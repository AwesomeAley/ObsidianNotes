Verify snort is installed 
`snort -V`

Test configuration file. **"-T"** is used for testing the config, **"-c"** is used for identifying the config (most likely in /etc/snort/snort.conf)
`sudo snort -c /etc/snort/snort.conf -T`

## Sniffer mode

| Parameter | Description                                      |
| --------- | ------------------------------------------------ |
| -v        | Verbose                                          |
| -d        | Display the packet (payload)                     |
| -e        | display the link-layer (TCP/IP/UDP/ICMP headers) |
| -X        | display the full packet details in HEX           |
| -i        | Define the network interface to listen/sniff     |

## Logger Mode

| Parameter | Description                                                                                                      |
| --------- | ---------------------------------------------------------------------------------------------------------------- |
| -l        | logger mode. Default output folder is **/var/log/snort**. Action is to dump as tcpdump format to this directory. |
| -k ASCII  | Log packets in ASCII format                                                                                      |
| -r        | read the dumped logs                                                                                             |
| -n        | specify the number of packets that will process/read                                                             |
