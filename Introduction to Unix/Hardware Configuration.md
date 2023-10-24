
### CPU
view information regarding your CPU by executing this command
	lscpu
For a more detailed look at your CPU's features, execute the following command:
	cat /proc/cpuinfo

### Memory
To display information about memory usage execute the following command
	free
For a more detailed breakdown of memory information, use the command
	cat  /proc/meminfo | less

### USB Devices
to view information on attached USB devices, use:
	lsusb

### Hardware Devices
To display hardware devices
	lspci
To display hardware devices along with their device code:
	lspci -nn 
To display information on a specific device:
	lspci -v -d *-device code-*

### SATA Drives
To display SATA drives on the system:
	ls /dev/sd*

Display kernel modules that are loaded into memory
	lsmod | less
	mod info : 
^command displays information on select module