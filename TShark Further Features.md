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

