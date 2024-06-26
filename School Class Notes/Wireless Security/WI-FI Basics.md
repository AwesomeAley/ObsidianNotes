[[Modulation]]
[[2.4 GHz and 5GHz Channels]]
[[802.11 Standards]]
[[WI-FI Frames]]

Remember that the primary goal of WI-FI is to create a local area network (WLAN). Connection to the internet is by means of an "upstream" wired connection, known as the distribution network.

The formal name of a WI-FI network's name is the SSID (Service Set Identifier).
The WI-FI standards define multiple types of service sets, or ways of forming a WLAN-topologies.
- Basic service set (BSS)
- Extended service set (ESS)
- Independent basic service set (IBSS)
- Mesh basic service set (MBSS)

## Basic Service Set (BSS)
The most common WI-FI topology
A single access point connects and associates with several client stations. Clients operate in infrastructure mode, which views the AP as the central connection point. In BSS clients cannot communicate with each other directly (of course they can so using higher-layer protocols, but all signals ultimately go through the AP).

The access point is typically also connected to distribution network such as an Ethernet LAN.

## Extended Service Set (ESS)
Used in larger networks to connect multiple access point to an Ethernet LAN, with APs having the same SSID. 
Enables configuration of seamless roaming, where a client station can roam from the service area of one access point into the service area of another access point without disrupting the connection.

## Independent Basic Service Set (IBSS)
No access point is needed; client stations form peer-to-peer relationships with other client stations.
Client devices must be configured in ad-hoc mode (not infrastructure mode)

## Mesh Basic Service Set (MBSS)
Used to provide coverage over a larger area without connecting every AP to the wired distribution source
Mesh points may communicate with each other on a different network than they provide to clients