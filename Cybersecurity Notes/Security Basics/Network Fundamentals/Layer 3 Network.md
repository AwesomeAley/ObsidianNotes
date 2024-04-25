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

There are not enough IPv4 addresses for every machine on the internet to have one.

We deal with this by having most machines connected to a Local Area Network (LAN) and their connection to the outside internet is mediated by a router that performs Network Address Translation (NAT) 

LAN IP Address Ranges
- 192.168.-
- 172.16.-.-  --- 172.31.-.-
- 10.-.-.-

### Dynamically Assigned IP Addresses
In the beginning, IP addresses of hosts on a network were statically assigned, and each machine had to be configured manually with its IP address
DHCP, the Dynamic Host Configuration Protocol, allows each device to be automatically assigned an IP address on demand, when it is connected
Note that this protocol must be implemented on a lower layer, since a machine that doesn't have en IP address yet cannot be located by such
DHCP is now virtually always used with Wi-Fi and is very prevalent on wired networks as well. 

### IPv6
Created to be a successor to IPv4, IPv6 is a 128 bit address scheme -- enough possible addresses for every interface on the planet to have a globally unique IP, forever

Addresses are written as 8 fields of 4 hexadecimal digits:
**2051:0011:13A2:0000:0000:03b2:000a:19aa**

Many IPv6 addresses have several groups of zeroes, and these can be abbreviated by a double :: 

Though all major operating systems now support IPv6, its adoption for the internet at large has been delayed seemingly indefinitely. Some people say NAT and DHCP are good enough as workarounds, but others disagree.