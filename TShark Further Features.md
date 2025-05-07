Capture packets and sort by color!
`tshark --color`

Filter captures with `tshark -z filter`

View protocol hierarchy to see a tree view of protocols used, frame numbers, and packet sizes.
 `tshark -r demo.pcapng -z io,phs -q`
Add filters to focus on specific protocols (for example UDP)
`tshark -r demo.pcapng -z io,udp -q`
View a table of packet sizes to identify anomalous sizes
`tshark -r demo.pcapng -z plen,tree -q`

View endpoint statistics and packets associated with each endpoint
`tshark -r demo.pcapng -z endpoints,ip -q`\
You can also sort by other p