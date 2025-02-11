### Configure General Settings
In the web interface, select `Device > Setup > Management`
Here you can set settings such as banner and domain

### Modify the Management Interface
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

### Check for Software Updates
Go to `Device > Software` to browse versions
You can hit `Check now` in the bottom left corner for check for new software

### Configure the DNS and NTP Servers
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

#### View Current Configuration

To see the full running configuration:

sh

CopyEdit

`show configuration`

To view a specific section, such as network settings:

sh

CopyEdit

`show configuration | match <keyword>`

---

### **Saving and Committing Changes**

After making configuration changes, you must commit them:

sh

CopyEdit

`commit`

If you want to see pending changes before committing:

sh

CopyEdit

`show config diff`

---

### **3. Load, Save, and Revert Configurations**

#### **Save Configuration to a Named Snapshot**

sh

CopyEdit

`save config to <filename.xml>`

Example:

sh

CopyEdit

`save config to backup-jan.xml`

#### **Load a Saved Configuration**

sh

CopyEdit

`load config from <filename.xml>`

Then commit the changes:

sh

CopyEdit

`commit`

#### **Revert to Last Saved Configuration (Before Last Commit)**

sh

CopyEdit

`revert config`

---

### **4. Export and Import Configurations**

#### **Export Running Configuration (via SCP or TFTP)**

sh

CopyEdit

`scp export configuration from running-config.xml to <user>@<server>:/path/`

Example:

sh

CopyEdit

`scp export configuration from running-config.xml to admin@192.168.1.10:/home/admin/`

#### **Import Configuration**

sh

CopyEdit

`scp import configuration from <user>@<server>:/path/<filename.xml>`

Then, load and commit:

sh

CopyEdit

`load config from <filename.xml> commit`

---

### **5. Set and Rollback Configuration Versions**

#### **View Configuration Versions**

sh

CopyEdit

`show config audit summary`

#### **Rollback to a Previous Version**

sh

CopyEdit

`rollback to version <X> commit`

(Replace `<X>` with the desired version number.)