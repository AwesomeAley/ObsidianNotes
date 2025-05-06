CLI version of wireshark

Helpful tools to pipe data into

| **Tool/Utility** | **Purpose and Benefit**                                                                                                                                |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **capinfos**     | A program that provides details of a specified capture file. It is suggested to view the summary of the capture file before starting an investigation. |
| **grep**         | Helps search plain-text data.                                                                                                                          |
| **cut**          | Helps cut parts of lines from a specified data source.                                                                                                 |
| **uniq**         | Filters repeated lines/values.                                                                                                                         |
| **nl**           | Views the number of shown lines.                                                                                                                       |
| **sed**          | A stream editor.                                                                                                                                       |
| **awk**          | Scripting language that helps pattern search and processing.                                                                                           |
|                  |                                                                                                                                                        |
| **Parameter**    | **Purpose**                                                                                                                                            |
| -h               | - Display the help page with the most common features.<br>- `tshark -h`                                                                                |
| -v               | - Show version info.<br>- `tshark -v`                                                                                                                  |
| -D               | - List available sniffing interfaces.<br>- `tshark -D`                                                                                                 |
| -i               | - Choose an interface to capture live traffic.<br>- `tshark -i 1`<br>- `tshark -i ens55`                                                               |
| **No Parameter** | - Sniff the traffic like tcpdump.<br>- `tshark`                                                                                                        |
