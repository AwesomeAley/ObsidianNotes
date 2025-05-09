## Configure General Settings
In the web interface, select `Device > Setup > Management`
Here you can set settings such as banner and domain

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

### Managing Configurations
#### Via GUI
Navigate to **Device > Setup > Operations**
![[Pasted image 20250211083311.png]]
Configurations can be rolledback, saved, loaded, exported, and imported as needed via .xml conifg files.

#### Via CLI

To see the full running configuration:
`show`

To view a specific section, such as network settings:
`show | match <keyword>`

If you want to see pending changes before committing:
`show config diff`

Save Configuration to a Named Snapshot
`save config to <filename.xml>`
	Example:
	`save config to backup-jan.xml`

Load a Saved Configuration
`load config from <filename.xml>`

Revert to Last Saved Configuration (Before Last Commit)
`revert config`

Export Running Configuration (via SCP or TFTP)
`scp export configuration from running-config.xml to <user>@<server>:/path/`
	Example:
	`scp export configuration from running-config.xml to admin@192.168.1.10:/home/admin/`

Import Configuration
`scp import configuration from <user>@<server>:/path/<filename.xml>`

Then, load and commit:
`load config from <filename.xml> commit`

View Configuration Versions
`show config audit summary`

Rollback to a Previous Version
`rollback to version <X> commit`


## Check for Software Updates
Go to `Device > Software` to browse versions
You can hit `Check now` in the bottom left corner for check for new software

## Configure the DNS and NTP Servers
In the web interface, select `Device > Setup > Services`
In the services window set the 
	- *Update Server* to: updates.paloaltonetworks.com
	- *Primary DNS Server* to: 8.8.8.8
	- *Secondary DNS Server* to: 192.168.50.53

Under the **NTP** tab, set the
	- *Primary NTP Server* to: 0.pool.ntp.org
	- *Secondary NTP Server* to: 1.pool.ntp.org



## Examine Log Files
Navigate to **Monitor > Logs**

#### Creating Log filters
filters are entered via search bar above table
elements can be selected to add them to the filter
![[Pasted image 20250211090402.png]]

The filter builder can be used to construct more advanced filters via the blue "plus" symbol to the left of the filter bar
For example:
![[Pasted image 20250211090825.png]]

