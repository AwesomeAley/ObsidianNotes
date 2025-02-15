	net**NOTE** - In documentation, ">" dictates operational mode, "#" dictates configuration mode. Configuration mode is activated with `configuration` and changes must be committed with `commit`

### Initial setup
Turn off the management interface and data external interface temporarily - you don't know who's accessing it
CLI:
```
# set deviceconfig system permitted-ip 127.0.0.1
# set network interface ethernet ethernet1/1 link-state down
```

Change the admin password
```
# set mgt-config users [USER] password 
[ENTER PASSWORD]
```
consider using an SSH key for authentication
https://docs.paloaltonetworks.com/pan-os/11-1/pan-os-admin/firewall-administration/manage-firewall-administrators/configure-administrative-accounts-and-authentication/configure-ssh-key-based-administrator-authentication-to-the-cli

review system info
`> show system info`

turn off dhcp-client on management interface
`# set deviceconfig system type static`

Only allow secure protocols to connect to the management interface (ssh, https, ping)
` > show system services`
```
# set deviceconfig system service disable-[SERVICE] [YES/NO]
```

Secure admin accounts
`> show admins all`
[[Managing Administrator Accounts]]

Turn data interfaces back on if turned off
`# set network interface ethernet ethernet1/1 link-state up`

### Modify the Management Interface
Navigate to `Device > Setup > Interfaces` and click on the `Management` interface

Set settings for the management interface on the firewall
Primarily the address and what service will be used to connect to the firewall
To the left add **permitted IP addresses** (addresses that are allowed management access)
	if empty all ips are authorized
![[Pasted image 20250210204238.png]]
#### Via CLI:
``` palo CLI
config
show deviceconfig system permitted-ip [ip addrews]
delete deviceconfig system permitted-ip [ip address]
set device config system permitted-ip [ip address]
commit
```
set the ip address for the management interface
 `set deviceconfig system ip-address <new-ip> netmask <subnet-mask> default-gateway <gateway-ip>`

Manage configurations as needed [[General Firewall Configurations]]

### Licensing and Updating
Navigate to **Device > Licenses > Activate feature using authorization code**
Activate with provided authorization code

Download all up-to-date updates/patches. Set up update schedules
![[Pasted image 20250212130951.png]]

