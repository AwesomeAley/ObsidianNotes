Bread and butter of the firewall. Police traffic as it flows in and out of your network.

Navigate to **Policies > Security** Click **Add**
*Security Policy Rule* windows contains multiple tabs
- **General** - Define name, rule type, description, tags
- **Source** - Define the source (zone, address, device) of traffic 
- **Destination** - Define the destination (zone, address, device) of traffic
- **Application and Service/URL Category** - Define the applications, services, and URLs involved in the rule.
	- The application-default setting instructs the firewall to allow an application such as web-browsing as long as that application is using the predefined service (or destination port).
- **Actions** - Define what you want your rule to do with defined traffic. Deny, allow, log etc.

**Hit count** is a valuable metric displayed on the policy table that can be used to determine whether a rule is being used or not. These can also be reset by highlighting the policy and clicking **Reset Rule Hit Counter** at the bottom right.