## Configure General Settings
In the web interface, select `Device > Setup > Management`
Here you can set settings such as banner and domain

## Modify the Management Interface
Navigate to `Device > Setup > Interfaces` and click on the `Management` interface

Set settings for the management interface on the firewall
Primarily the address and what service will be used to connect to the firewall
To the left add **permitted IP addresses** (addresses that are allowed management access)
![[Pasted image 20250210204238.png]]
#### Via CLI:
``` palo CLI
config
show deviceconfig system permitted-ip [ip addrews]
delete deviceconfig system permitted-ip [ip address]
set device config system permitted-ip [ip address]
commit
```

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


## Examine Log Files
Navigate to **Monitor > Logs**

#### Creating Log filters
filters are entered via search bar above table
elements can be selected to add them to the filter
![[Pasted image 20250211090402.png]]

The filter builder can be used to construct more advanced filters via the blue "plus" symbol to the left of the filter bar

Tue feb 11 14:59:54 2025