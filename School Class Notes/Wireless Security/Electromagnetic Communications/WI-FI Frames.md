
Because of the complex nature of broadcast communication, 802.11 has three frame types, each with multiple sub-types

### Three types of WI-FI frames
**Date Frames (type 02)**
- carry the actual data passed down from the higher-layer protocols
**Control Frames (type 01)**
- assist with the delivery of data frames
- contain only header information
**Management Frames (type 00)**
- used for joining and leaving a network
the 4-but subtype field determines the frame name

### Control frame subtypes

| subtype field | Name                    |
| ------------- | ----------------------- |
| 0100          | Beamforming report poll |
| 0101          | VHT/HE NDP Announcement |
| 0110          | Control Frame Extension |
| 0111          | Control wrapper         |
| 1000          | Block ACK Request       |
| 1001          | Block ACK               |
| 1010          | PS-Poll                 |
| 1011          | RTS                     |
| 1100          | CTS                     |
| 1101              | ACK                        |

Since wi-fi is a broadcast technology, there is no way to know that a frame has been received.
Upon receiving most types of frames, the receiver must respond with an ACK control frame to acknowledge that the frame was received.

Most 802.11 data frames carry actual data that is passed down from higher-layer protocols
**QoS (Quality of Service)** frames contain an "Access Category" field that can be used to prioritize delivery.

### Management Frame Subtypes

#### Beacon Frames
An AP continuously transmits beacons on the selected RF band and channel to advertise its presence and configuration.
- A beacon is transmitted as a broadcast, with the destination MAC address being set to "ALL".
Beacons also contain timing and synchronization information needed for connecting.
- "The heartbeat of the wireless network"
An AP sends beacons at a rate of one every 102.4 milliseconds
Clients only transmit beacons in ad-hoc mode

