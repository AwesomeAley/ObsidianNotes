Multiple internet-facing applications may be run on a machine with a single IP address.
- IP packets intended for one application should not be sent to a different one.
This problem (among others) is solved by a layer 4 protocls on top of IP: **The Transport Layer**
- The TCP and UDP protocols exist at this level
The transport layer protocol define number ports to specify multiple destinations on the same host
- The port number can be written with a colon after the IP address
- Example: 50.194.112.179:80

TCP creates a persistent connection between ports on two hosts for sending arbitrarily long data stream, on top of the lossy packet based IP protocol

The **Three way handshake** establishes the connection, verifying that both hosts can receive and respond to requests. Both hosts maintain a connection table that associates an IP address and port with each connection until it is terminated or times out.
TCP **Sequence Numbers** are monitored in order to 
- request re-send of lost packets
- put received packets back in the correct order