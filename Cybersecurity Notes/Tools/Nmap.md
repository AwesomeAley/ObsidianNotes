Nmap (“Network Mapper”) is an open source tool for network exploration and security auditing. It was designed to rapidly scan large networks, although it works fine against single hosts
**Reference**
https://nmap.org/book/man.html
#### Usage
`nmap <range of hosts (10.0.0.0-255)>

#### Flags
to find information on flags, run the nmap command with no arguments. Noteworthy flags:

`-sP`= skip port scan (used for scanning for listening addresses)
`-A `= enable OS and version detection, scriptscanning, traceroute
`-T4`= for faster execution