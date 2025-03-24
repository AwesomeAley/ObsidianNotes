Nmap (“Network Mapper”) is an open source tool for network exploration and security auditing. It was designed to rapidly scan large networks, although it works fine against single hosts
**Reference**
https://nmap.org/book/man.html
#### Usage
`nmap <range of hosts (10.0.0.0-255)>

#### Important Switches
to find information on flags, run the nmap command with no arguments. Noteworthy flags:

**Types of Connections**
`-sT`= commit scan with TCP
`-sS`= commit scan with SYN (stealthier)
`-sU`= commit scan with UDP
`-sN, -sF, -sX`= commit scan with NULL, FIN, or XMAS
these can be used to attempt to bypass firewalls
`-sN`= commit scan with ICMP ping (ignores ports)
`-sV`= version detection

`-p <port range, - for all.`= specify ports
`-sP`= skip port scan (used for scanning for listening addresses)
`-A `= enable OS and version detection, scriptscanning, traceroute
`-T4`= for faster execution


**Scripts**
scripts are stored in /usr/share/nmap/scripts
`-script=<script name>`= run a script
