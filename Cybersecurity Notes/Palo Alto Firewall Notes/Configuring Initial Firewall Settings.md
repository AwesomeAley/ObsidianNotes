### Configure the DNS and NTP Servers
In the web interface, select `Device > Setup > Services`
In the services window set the 
	- *Update Server* to: updates.paloaltonetworks.com
	- *Primary DNS Server* to: 8.8.8.8
	- *Secondary DNS Server* to: 192.168.50.53

Under the **NTP** tab, set the
	- *Primary NTP Server* to: 0.pool.ntp.org
	- *Secondary NTP Server* to: 1.pool.ntp.org

### Configure General Settings
In the web interface, select `Device > Setup > Management`
Here you can set settings such as banner and domain

### Modify the Management Interface
Navigate to `Device > Setup > Interfaces` and click on the `Management` interface

Set settings for the management interface on the firewall
Primarily the address and what service will be used to connect to the firewall
![[Pasted image 20250210201003.png]]

