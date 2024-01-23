Multiple internet-facing applications may be run on a machine with a single IP address.
- IP packets intended for one application should not be sent to a different one.
This problem (among others) is solved by a layer 4 protocls on top of IP: **The Transport Layer**
- The TCP and UDP protocols exist at this level
The transport layer protocol define number ports to specify multiple destinations on the same host
- The port number can be written with a colon after the IP address
- Example: 50.194.112.179:80

TCP creates a persistent connection between ports on two hosts for sending arbitrarily long data stream, on top of the lossy packet based IP protocol