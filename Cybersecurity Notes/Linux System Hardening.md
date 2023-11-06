
*#* Need to create a publicly available linux hardening guide for beginners with commands 
information gathering for this starts here
https://security.utexas.edu/os-hardening-checklist/linux-7#1

The following checklist details steps to harden systems running Linux based operating systems.  [[-Intro to Unix]] for further information on terminal usage.


## Preparation and Installation
#### Set a BIOS/firmware password

#### Update Systems
	apt update

#### Install Yum Security Plugin
###### Install the yum security plugin:
	yum install yum-security

###### List updates that are security relevant
	yum --security check-update

###### To apply updates that are security relevant
	yum --security update


#### Set a BIOS/firmware password
