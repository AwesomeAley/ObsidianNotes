## IPv4 Addressing
Fundamental to moving data to its destination on a network is a system for identifying those destinations-*addressing*.
AN IPv4 address is 32 bits, written as four 8 bit number, or octets (between 0 and 255)
Routers direct IP packets one "hop" closer to their destination
LANs use private IP addresses and communicate with the global internet with the help of the NAT protocol

DHCP, the dynamic host configuration protocol, allows each device to be automatically assigned an IP address on demand when it is connected. This allows greater mobility of devices.
### Subnet Masks
The left bits of an IP address are the same for all addresses on a given network; the right bits identify an individual host.
Where the split is between the network and the host part can  vary
A subnet mask is a 32-bit string where the bits corresponding to the network are all 1's and the bits corresponding to the host are all zeroes.

![[Pasted image 20240118115447.png]]

