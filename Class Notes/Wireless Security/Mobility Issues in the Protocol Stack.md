The increased *host mobility* associated with wireless networking has implications all through the protocol stack, and presents many challenges.
Many current network protocols were designed and secured with static devices in mind. 
- Lan protocols such as ethernet assume that the interface would remain connected and secure
However, wireless devices must be usable from any location, and ideally should also be usable when in transit between locations, often switching between WI-FI and Cellular networks
If the IP address of a host changes, any active TCP session will be disconnected.

#### De-coupling layers can help mobility
Even if the ethernet and ip addresses change
Higher layer sessions should remain active such as logging into your banking app, connecting to a game server, or shopping site state remaining active

**Main Idea**: Don't use lower-layer data to identify application-layer sessions,
- use cookies not IP addresses
- re-establish a TCP connection with the same upper-layer session data