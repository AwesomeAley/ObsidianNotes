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

