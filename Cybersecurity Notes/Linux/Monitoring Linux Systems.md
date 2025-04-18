
#### To monitor currently running processes use the [[ps Command]]

`ps aux`
The `ps` command is used when you want to view information about processes running on a Unix/Linux system. It is essential for managing system resources, diagnosing issues, and understanding system behavior.


The `ps` command can be used without any options to list processes that belong to the current user and are associated with the terminal where the command is run.

**Parameters (flags):**
`-A` display information on all processes running on the system
`-a` displays processes from all users
`-u` includes user-orientated information such as cpu/memory usage
`-f` display additional information on processes

The trick is to pipe the command into grep to look for specific processes



#### To monitor connections over the network use the [[netstat Command]]

Execute the netstat command alone to show a relatively simple list of all active tcp connections for the device which, for each one, will show the local Ip Address (your computer), the foreign IP address (the other computer or network device), along with their respective port numbers, as well as the TCP state.

`netstat -nalp`

**Parameters (flags)** Syntax

| **-a**            | This switch displays active TCP connections, TCP connections with the listening state, as well as UDP ports that are being listened to.                                                                                                                                                                             |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **-b**            | This netstat switch is very similar to the **-o** switch listed below, but instead of displaying the PID, will display the process's actual file name. Using **-b** over **-o** might seem like it's saving you a step or two but using it can sometimes greatly extend the time it takes netstat to fully execute. |
| **-e**            | Use this switch with the netstat command to show statistics about your network connection. This data includes bytes, unicast packets, non-unicast packets, discards, errors, and unknown protocols received and sent since the connection was established.                                                          |
| **-f**            | The **-f** switch will force the netstat command to display the [Fully Qualified Domain Name](https://www.lifewire.com/what-does-fqdn-mean-2625883) (FQDN) for each foreign IP addresses when possible.                                                                                                             |
| **-n**            | Use the **-n** switch to prevent netstat from attempting to determine [host names](https://www.lifewire.com/what-is-a-hostname-2625906) for foreign IP addresses. Depending on your current network connections, using this switch could considerably reduce the time it takes for netstat to fully execute.        |
| **-o**            | A handy option for many troubleshooting tasks, the **-o** switch displays the process identifier (PID) associated with each displayed connection. See the example below for more about using **netstat -o**.                                                                                                        |
| **-p**            | Use the **-p** switch to show connections or statistics only for a particular _protocol_. You can not define more than one _protocol_ at once, nor can you execute netstat with **-p** without defining a _protocol_.                                                                                               |
| _protocol_        | When specifying a _protocol_ with the **-p** option, you can use **tcp**, **udp**, **tcpv6**, or **udpv6**. If you use **-s** with **-p** to view statistics by protocol, you can use **icmp**, **ip**, **icmpv6**, or **ipv6** in addition to the first four I mentioned.                                          |
| **-r**            | Execute netstat with **-r** to show the IP routing table. This is the same as using the route command to execute **route print**.                                                                                                                                                                                   |
| **-s**            | The **-s** option can be used with the netstat command to show detailed statistics by protocol. You can limit the statistics shown to a particular protocol by using the **-s**option and specifying that _protocol_, but be sure to use **-s** before **-p** _protocol_ when using the switches together.          |
| **-t**            | Use the **-t** switch to show the current TCP chimney offload state in place of the typically displayed TCP state.                                                                                                                                                                                                  |
| **-x**            | Use the **-x** option to show all NetworkDirect listeners, connections, and shared endpoints.                                                                                                                                                                                                                       |
| **-y**            | The **-y** switch can be used to show the TCP connection template for all connection. You cannot use **-y** with any other netstat option.                                                                                                                                                                          |
| _time_in__terval_ | This is the time, in seconds, that you'd like the netstat command to re-execute automatically, stopping only when you use [Ctrl-C](https://www.lifewire.com/what-is-ctrl-c-used-for-2625834) to end the loop.                                                                                                       |
| **/?**            | Use the [help switch](https://www.lifewire.com/help-switch-2625896) to show details about the netstat command's several options.                                                                                                                                                                                    |
