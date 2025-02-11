Network interfaces display information on the network behind cables connected to certain interfaces on the firewall device

**network > interfaces**
![[Pasted image 20240215132718.png]]

for example the interface "ethernet1/3" is labeled as external here. This is the outbound connection

### Management Policies
Policies that can be applied to interfaces dictating whether management traffic is allowed (ping, ssh, https, etc)

Navigate to **Network > Network Profiles > Interface Mgmt**.
Click "add" and configure management profile, check marking what services you want to allow and defining permitted ip addresses (empty if all)

This will not block normal traffic

