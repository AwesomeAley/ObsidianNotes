### Installation:
**On Linux** (With relevant installer)
```bash
apt install wireshark
```

### Basic Filtering
**Documentation:** https://wiki.wireshark.org/DisplayFilters

Basic syntax involves  (protocol).(filter parameter) == (value)
for example: 
```
ip.addr == <ip address> 
```

Filtering by SRC and DST: The second filter will look at is two in one as well as a filter operator: ip.src and ip.dst. These filters allow us to filter the traffic by the source and destination from which the traffic is coming from.
```
ip.src == <SRC IP Address> and ip.dst == <DST IP Address>
```
 
Wireshark can filter by both port numbers as well as protocol names.
```
tcp.port eq <Port #> or <Protocol Name>
```
You can also filter for udp `udp.port == <port #>`


### Built in Features
Organize the protocols present in a capture using the Protocol Hierarchy. 
Navigate to Statistics > Protocol Hierarchy.

(For HTTP)This feature will allow us to organize all requested URIs in the capture. To use Export HTTP Object navigate to file > Export Objects > HTTP.

Organize all endpoints and IPs found within a specific capture.  To use the Endpoints feature
navigate to Statistics > Endpoints.