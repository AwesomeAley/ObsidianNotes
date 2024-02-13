### Passive and Active Scanning
The first step to connecting to a wi-fi network is to become aware of its existence and parameters.
A client in the scanning process is in state 1
In **passive scanning** the wireless client simply listens for beacons from APs on multiple channels.

With **active scanning** the client proactively scans the network by sending out probe request frames, to be answered by a  probe response from the AP.
- The probe response has the same information as a beacon frame
A probe request may be directed (intended for a single SSID of an AP) or null (intended to be answered by any APs that receive it)

### The Connection Process
Joining a network is a two-step process, first **authentication** and then **association** with an Access Point The process creates a layer 2 connection

NOTE: what is called authentication here is not (anymore) the secure process of verifying user identity or knowledge of the passkey. That comes later. It is really more of a handshake, or verification that both devices are 802.11 verified.
For this reason it is called "open" authentication.

### Part 1: Authentication (Open)
1. The client listens for Beacon frames that match a selected SSID and with compatible protocol versions (or in active scanning, sends probe request frames)
2. The client sends an authentication request frame with a sequence number 1 to an AP, setting the authentication to open
3. The AP responds with an authentication response frame with sequence number 2, also set to open

### Part 2: Association
1. Client sends an association request frame to the AP. The request contains chosen encryption types if required.



Notes on Authentication and Association
A client can actually be *authenticated* to multiple APs at the same time, though not associated. This can speed up the association process when moving between APs.

Besides open authentication, shared-key authentication was sometimes used in conjunction with WEP security.

### Disassociation and Deauthentication
Either a client or AP may send a disassociation frame to terminate the association. It is the polite wat to leave a WLAN. It is a notification, not a request; cannot be refused by any party (unless the frame's integrity check fails).

Deauthentication frames automatically cause disassociation as well, since authentication is required for association. Deauthentication frames are commonly sent by APs to kick off devices. These frames can also be sent by malicious parties are part of an attack. 

Integration with the wired Layer 2 network
To forward WI=FI frames onto a wired network, the AP must reframe the 802.11 frames as 802.3 Ethernet frames. This technology is called **integration Service (IS)**
Removes the 802.11 frame header and footer, then adds 802.3 header and footer to the frame body.
Management and control frames are purely for the MAC sublayer and have no need to be translated by the integration service.

