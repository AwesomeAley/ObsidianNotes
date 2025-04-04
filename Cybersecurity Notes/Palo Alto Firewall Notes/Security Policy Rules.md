Bread and butter of the firewall. Police traffic as it flows in and out of your network.
**IMPORTANT** Rules are top-to-bottom, so the firewall checks the rule list top to bottom until a rule matches. It will stop after the first match.
### Creating Policies
Navigate to **Policies > Security** Click **Add**
*Security Policy Rule* windows contains multiple tabs
- **General** - Define name, rule type, description, tags
- **Source** - Define the source (zone, address, device) of traffic 
- **Destination** - Define the destination (zone, address, device) of traffic
- **Application and Service/URL Category** - Define the applications, services, and URLs involved in the rule.
	- The application-default setting instructs the firewall to allow an application such as web-browsing as long as that application is using the predefined service (or destination port).
	- This section can be used to allow functions such as ping or web-browsing
- **Actions** - Define what you want your rule to do with defined traffic. Deny, allow, log etc.

### Determining Policy Details
Two default rules automatically exist. The *intra-zone* rule governs traffic between interfaces of the same zone, while the *inter-zone* rule governs traffic between interfaces of two different zones.
![[Pasted image 20250212101947.png]]

The firewall is a stateful firewall; if outbound traffic is allowed, reply traffic will be dynamically allowed. Therefore focus initial rules on outbound traffic from trusted zones.
### Monitoring Effectiveness
**Hit count** is a valuable metric displayed on the policy table that can be used to determine whether a rule is being used or not. These can also be reset by highlighting the policy and clicking **Reset Rule Hit Counter** at the bottom right.

### Security Profiles
You will also want to set [[Security Profiles]] for all inbound and outbound traffic to improve monitoring, detection, and protection.