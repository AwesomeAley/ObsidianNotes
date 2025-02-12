Turn off the management interface and data external interface temporarily - you don't know who's accessing it
CLI:
```
configure
set deviceconfig system permitted-ip 127.0.0.1
set network interface ethernet ethernet1/1 link-state down
commit
```

Change the admin password
```
configure
set mgt-config users [USER] password
[ENTER PASSWORD]
commit
```
consider using an SSH key for authentication
https://docs.paloaltonetworks.com/pan-os/11-1/pan-os-admin/firewall-administration/manage-firewall-administrators/configure-administrative-accounts-and-authentication/configure-ssh-key-based-administrator-authentication-to-the-cli
