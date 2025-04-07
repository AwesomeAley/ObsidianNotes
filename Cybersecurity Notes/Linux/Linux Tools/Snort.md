Verify snort is installed 
`snort -V`

Test configuration file. **"-T"** is used for testing the config, **"-c"** is used for identifying the config (most likely in /etc/snort/snort.conf)
`sudo snort -c /etc/snort/snort.conf -T`

## Sniffer mode

| Parameter | Description                                      |
| --------- | ------------------------------------------------ |
| -v        | Verbose                                          |
| -d        | Display the packet (payload)                     |
| -e        | display the link-layer (TCP/IP/UDP/ICMP headers) |
| -X        | display the full packet details in HEX           |
| -i        | Define the network interface to listen/sniff     |

## Logger Mode

| Parameter | Description                                                                                                                                                                                            |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| -l        | logger mode. Default output folder is **/var/log/snort**. Action is to dump as tcpdump format to this directory. Directory can also be specified after. For example: `-l .` dumps to current directory |
| -k ASCII  | Log packets in ASCII format                                                                                                                                                                            |
| -r        | read the binary logs. Can also be used to filter. Ex: `sudo snort -r tcp and port 80'                                                                                                                  |
| -n        | specify the number of packets that will process/read                                                                                                                                                   |

Start logger mode with logs in ASCII format saved to current directory
`sudo snort -dev -K ASCII -l .`

## IDS/IPS Mode

### Detection:
`snort -c /etc/snort[rule or config file]`

| Parameter | Description                                                                                  |
| --------- | -------------------------------------------------------------------------------------------- |
| -c        | define config file                                                                           |
| -D        | background mode                                                                              |
| -A        | Alert Modes:<br> **full**<br> **fast**: less info<br> **console**: provide alerts in console |
### Prevention:
Activated with `-Q --daq` parameters. Also requires identifying interfaces (at least 2)
Example:
`snort -c /etc/snort/snort.conf -q -Q --daq afpacket -i eth0:eth1 -A console`


