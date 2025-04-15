Check Zeek version and if it is installed
`zeek -v`

Start Zeek as a service (control module)
`zeekctl`

*within the control module*
`status`
`start`
`stop`

## PCAP Reading Mode

`zeek -C -r sample.pcap`

Logs will be generated into the current directory

| Parameter | Description                           |
| --------- | ------------------------------------- |
| -r        | reading option to process a pcap file |
| -C        | ignore checksum errors                |
### Log reading
An example of the usages of some important logs

| **Overall Info**     | **Protocol Based** | **Detection**    | **Observation**      |
| -------------------- | ------------------ | ---------------- | -------------------- |
| _conn.log_           | _http.log_         | _notice.log_     | _known_host.log_     |
| _files.log_          | _dns.log_          | _signatures.log_ | _known_services.log_ |
| _intel.log_          | _ftp.log_          | _pe.log_         | _software.log_       |
| _loaded_scripts.log_ | _ssh.log_          | _traceroute.log_ | _weird.log_          |

`zeek-cut` can be used to sort based on *#fields* which are in the log files
example: `cat conn.log | zeek-cut uid proto id.orig_h id.orig_p id_resp_h id.resp_p`

## Zeek Signatures

Run Zeek with signature file
`zeek -C -r sample.pcap -s sample.sig`

Zeek signature files use the *.sig* extension.

Zeek signatures are composed of three logical paths; signature id, conditions and action. The signature breakdown is shown in the table below;

| **Signature id** | **Unique** signature name.                                                                                                                                                                                          |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Conditions**   | **Header:** Filtering the packet headers for specific source and destination addresses, protocol and port numbers.<br><br>**<br><br>**Content:** Filtering the packet payload for specific value/pattern.<br><br>** |
| **Action**       | **Default action:** Create the "signatures.log" file in case of a signature match.<br><br>**Additional action:** Trigger a Zeek script.                                                                             |

Now let's dig more into the Zeek signatures. The below table provides the most common conditions and filters for the Zeek signatures.

| Condition Field               | Available Filters                                                                                                                                                                                                                                                                                                                                                |     |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| Header                        | src-ip: Source IP.<br><br>dst-ip: Destination IP.<br><br>src-port: Source port.<br><br>dst-port: Destination port.<br><br>ip-proto: Target protocol. Supported protocols; TCP, UDP, ICMP, ICMP6, IP, IP6                                                                                                                                                         |     |
| Content                       | **payload:** Packet payload.  <br>**http-request:** Decoded HTTP requests.  <br>**http-request-header:** Client-side HTTP headers.  <br>**http-request-body:** Client-side HTTP request bodys.  <br>**http-reply-header:** Server-side HTTP headers.  <br>**http-reply-body:** Server-side HTTP request bodys.  <br>**ftp:** Command line input of FTP sessions. |     |
| **Context**                   | **same-ip:** Filtering the source and destination addresses for duplication.                                                                                                                                                                                                                                                                                     |     |
| Action                        | **event:** Signature match message.                                                                                                                                                                                                                                                                                                                              |     |
| **Comparison  <br>Operators** | **==**, **!=**, **<**, **<=**, **>**, **>=**                                                                                                                                                                                                                                                                                                                     |     |
| **NOTE!**                     | Filters accept string, numeric and regex values.                                                                                                                                                                                                                                                                                                                 |     |
**Example Signature File**
```bash
#example
signature ftp-username { 
	ip-proto == tcp 
	ftp /.*USER.*/ 
	event "FTP Username Input Found!" } 
	
signature ftp-brute { 
	ip-proto == tcp 
	payload /.*530.*Login.*incorrect.*/ 
	event "FTP Brute-force Attempt!" }
```

## Scripting
files use the .zeek extension

| Script Directory                               | path                                 |
| ---------------------------------------------- | ------------------------------------ |
| default zeek scripts                           | /opt/zeek/share/zeek/base            |
| user generated scripts                         | /opt/zeek/share/zeek/site            |
| policy scripts                                 | /opt/zeek/share/zeek/policy          |
| script config file to run scripts in live mode | /opt/zeek/share/zeek/site/local.zeek |
Running with script
`zeek -r sample.pcap sample.zeek`
Running with signature and script
`zeek -r sample.pcap -s sample.sig sample.zeek`
Running with all local scripts
`zeek -r sample.pcap local`
