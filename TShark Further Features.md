Capture packets and sort by color!
`tshark --color`

Filter captures with `tshark -z filter`

View protocol hierarchy to see a tree view of protocols used, frame numbers, and packet sizes.
 `tshark -r demo.pcapng -z io,phs -q`
Add filters to focus on specific protocols (for example UDP)
`tshark -r demo.pcapng -z io,phs,udp -q`
View a table of packet sizes to identify anomalous sizes
`tshark -r demo.pcapng -z plen,tree -q`

## Endpoints
View endpoint statistics and packets associated with each endpoint
`tshark -r demo.pcapng -z endpoints,ip -q`\
You can also sort by other parameters other than "ip"

| **Filter** | **Purpose**                                       |
| ---------- | ------------------------------------------------- |
| eth        | - Ethernet addresses                              |
| ip         | - IPv4 addresses                                  |
| ipv6       | - IPv6 addresses                                  |
| tcp        | - TCP addresses<br>- Valid for both IPv4 and IPv6 |
| udp        | - UDP addresses<br>- Valid for both IPv4 and IPv6 |
| wlan       | - IEEE 802.11 addresses                           |

## Conversations
View traffic flow between connection points
`tshark -r demo.pcapng -z conv,ip -q`

View expert comments
`tshark -r demo.pcapng -z expert -q`

## Filters for Specific Protocols
Filter by protocol
`tshark -r demo.pcapng -z ptype,tree -q`

Filter by ip addresses
IPv4: `tshark -r demo.pcapng -z ip_hosts,tree -q'
IPv6: `tshark -r demo.pcapng -z ipv6_hosts,tree -q'

Filter by source or destination address
Source
	IPv4: `tshark -r demo.pcapng -z ip_srcdst,tree -q'
	IPv6: `tshark -r demo.pcapng -z ipv6_srcdst,tree -q'
Destination
	IPv4: `tshark -r demo.pcapng -z dests,tree -q'
	IPv6: `tshark -r demo.pcapng -z ipv6_dests,tree -q'

Filter by DNS
`tshark -r demo.pcapng -z dns,tree -q'
Filter by HTTP
- **Packet and status counter for HTTP:** `-z http,tree -q`
- **Packet and status counter for HTTP2:** `-z http2,tree -q`
- **Load distribution:** `-z http_srv,tree -q`
- **Requests:** `-z http_req,tree -q`
- **Requests and responses:** `-z http_seq,tree -q`

## Streams
Follow traffic streams
- **TCP Streams:** `-z follow,tcp,ascii,0 -q`
- **UDP Streams:** `-z follow,udp,ascii,0 -q`
- **HTTP Streams:** `-z follow,http,ascii,0 -q`

| **Main Parameter** | **Protocol**                        | **View Mode**    | **Stream Number**    | **Additional Parameter** |
| ------------------ | ----------------------------------- | ---------------- | -------------------- | ------------------------ |
| -z follow          | - TCP<br>- UDP<br>- HTTP<br>- HTTP2 | - HEX<br>- ASCII | 0 \| 1 \| 2 \| 3 ... | -q                       |
## Export options
This option helps analysts to extract files from DICOM, HTTP, IMF, SMB and TFTP. The query structure is explained in the table given below.

| **Main Parameter** | **Protocol**                                  | **Target Folder**                | **Additional Parameter** |
| ------------------ | --------------------------------------------- | -------------------------------- | ------------------------ |
| --export-objects   | - DICOM<br>- HTTP<br>- IMF<br>- SMB<br>- TFTP | Target folder to save the files. | -q                       |

You can filter the packets and follow the streams by using the parameters given below.  

- `--export-objects http,/home/ubuntu/Desktop/extracted-by-tshark -q`

## Credentials
Detect cleartext credentials
`tshark -r demo.pcapng -z credentials -q`

## Extract
*Note:* You can use "contains" and "matches" just like in Wireshark GUI
![[Pasted image 20250507152632.png]]


This option helps analysts to extract specific parts of data from the packets. In this way, analysts have the opportunity to collect and correlate various fields from the packets. It also helps analysts manage the query output on the terminal. The query structure is explained in the table given below.

|                 |                  |                     |
| --------------- | ---------------- | ------------------- |
| **Main Filter** | **Target Field** | **Show Field Name** |
| -T fields       | -e <field name>  | -E header=y         |

**Note:** You need to use the -e parameter for each field you want to display.

You can filter any field by using the field names as shown below.

- `-T fields -e ip.src -e ip.dst -E header=y`
