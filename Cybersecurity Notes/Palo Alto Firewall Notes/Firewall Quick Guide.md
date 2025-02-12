**NOTE** - In documentation, ">" dictates operational mode, "#" dictates configuration mode. Configuration mode is activated with `configuration` and changes must be committed with `commit`

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
