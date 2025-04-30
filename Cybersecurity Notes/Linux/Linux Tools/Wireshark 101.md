## Installation:
**On Linux** (With relevant installer)
```bash
apt install wireshark
```

## Basic Filtering
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

### TCP and UDP Filtering

| Filter                | Description                                     | Filter                | Expression                                      |
| --------------------- | ----------------------------------------------- | --------------------- | ----------------------------------------------- |
| `tcp.port == 80`      | Show all TCP packets with port 80               | `udp.port == 53`      | Show all UDP packets with port 53               |
| `tcp.srcport == 1234` | Show all TCP packets originating from port 1234 | `udp.srcport == 1234` | Show all UDP packets originating from port 1234 |
| `tcp.dstport == 80`   | Show all TCP packets sent to port 80            | `udp.dstport == 5353` | Show all UDP packets sent to port 5353          |
### Application Level Filtering
| Filter                          | Description                                    | Filter                    | Description              |
| ------------------------------- | ---------------------------------------------- | ------------------------- | ------------------------ |
| `http`                          | Show all HTTP packets                          | `dns`                     | Show all DNS packets     |
| `http.response.code == 200`     | Show all packets with HTTP response code "200" | `dns.flags.response == 0` | Show all DNS requests    |
| `http.request.method == "GET"`  | Show all HTTP GET requests                     | `dns.flags.response == 1` | Show all DNS responses   |
| `http.request.method == "POST"` | Show all HTTP POST requests                    | `dns.qry.type == 1`       | Show all DNS "A" records |
### Built in Features
Organize the protocols present in a capture using the Protocol Hierarchy. 
Navigate to Statistics > Protocol Hierarchy.

(For HTTP)This feature will allow us to organize all requested URIs in the capture. To use Export HTTP Object navigate to file > Export Objects > HTTP.

Organize all endpoints and IPs found within a specific capture.  To use the Endpoints feature
navigate to Statistics > Endpoints.

### Statistics info
**statistics** > **resolved addresses** : list all ip addresses and domain names found in capture
**statistics** > **protocol hierarchy** : list all protocols found in capture
**statistics** > **conversations** : list all conversations between endpoints found in capture
**statistics** menu contains many more useful info windows such as DNS, HTTP, and IPvX statistics