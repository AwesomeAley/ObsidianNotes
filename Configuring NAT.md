Internal private ip addresses need to be converted to a single public-facing address, This needs to be configured via *NAT Policies*. 

Navigate to **Policies > NAT**. Click **Add** to create a new policy.

First create a policy for inbound zones to internet
In the *NAT Policy Rule* window, configure the *general* tab with name, description, and NAT type; most likely ipv4.

In the *original packet* tab, configure source internal zones and then destination "internet" zone with associated interface/service as needed.
![[Pasted image 20250212114210.png]]

