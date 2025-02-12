Internal private ip addresses need to be converted to a single public-facing address, This needs to be configured via *NAT Policies*. 


## Create a Source NAT Policy
Navigate to **Policies > NAT**. Click **Add** to create a new policy.

First create a policy for inbound zones to internet
In the *NAT Policy Rule* window, configure the *general* tab with name, description, and NAT type; most likely ipv4.

In the *original packet* tab, configure source internal zones and then destination external zone with associated interface/service as needed.

In my example my source is my two internal zones, destination is my "internet" zone and its interface:
![[Pasted image 20250212114210.png]]

In the *translated packet* tab, configure what address you want the source packet to be translated to. 

In my example, I want it translated to the external facing interface of `ethernet1/1` with its associated public address of `203.0.113.20/24`:
![[Pasted image 20250212114434.png]]
## Create a Destination NAT Policy
Navigate to **Policies > NAT**. Click **Add** to create a new policy.

