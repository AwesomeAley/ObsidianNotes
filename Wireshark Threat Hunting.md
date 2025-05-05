
## Nmap Scans
Spot Nmap network scans on network traffic

| **Notes**                                                                                | **Wireshark Filters**                                                          |
| ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Global search.                                                                           | - `tcp`<br><br>- `udp`                                                         |
| - Only SYN flag.<br>- SYN flag is set. The rest of the bits are not important.           | - `tcp.flags == 2`<br><br>- `tcp.flags.syn == 1`                               |
| - Only ACK flag.<br>- ACK flag is set. The rest of the bits are not important.           | - `tcp.flags == 16`<br><br>- `tcp.flags.ack == 1`                              |
| - Only SYN, ACK flags.<br>- SYN and ACK are set. The rest of the bits are not important. | - `tcp.flags == 18`<br><br>- `(tcp.flags.syn == 1) and (tcp.flags.ack == 1)`   |
| - Only RST flag.<br>- RST flag is set. The rest of the bits are not important.           | - `tcp.flags == 4`<br><br>- `tcp.flags.reset == 1`                             |
| - Only RST, ACK flags.<br>- RST and ACK are set. The rest of the bits are not important. | - `tcp.flags == 20`<br><br>- `(tcp.flags.reset == 1) and (tcp.flags.ack == 1)` |
| - Only FIN flag<br>- FIN flag is set. The rest of the bits are not important.            | - `tcp.flags == 1`<br><br>- `tcp.flags.fin == 1`                               |

Filter to find TCP Connect scan patterns in a capture file to easier locate tcp handshakes
``tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024``

Filter to find TCP SYN scan patterns in capture file
``tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024`
