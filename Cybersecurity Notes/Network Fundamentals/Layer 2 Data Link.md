As Layer 3 is dominated by the IP protocol, Layer 2 is primarily the Ethernet protocol; IEEE 802.3.
The word "Ethernet" is also used in regard to the physical layer but at layer 2 we are referring to the ethernet protocol which can be used on top of different physical substrates (including WI-FI). This is designed to connect data on machines on the same LAN. We use IP addresses to identify machines on local networks as well, but it depends on layer 2.

Important to layer 2 protocols is dealing with collisions that occur when multiple machines transmit data at the same time. 

As the canonical layer 3 device is the router, the canonical layer 2 device is the switch.

### MAC Addresses and Ethernet Frames
Ethernet interface devices are identified by a 48-bit MAC address. These are written as 6 octets in hexadecimals: 5C:BA:EF:18:06:A)

Unlike IP addresses, there are uniquely assigned to each hardware device by the manufacturer (though they can be spoofed).

The unit of transmission for the Ethernet is called the *Frame*, and unlike IP packets it has both a header and a footer. 

![[Pasted image 20240123114345.png]]