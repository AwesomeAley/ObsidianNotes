## Initial Setup
Download tools or the entire suite from https://learn.microsoft.com/en-us/sysinternals/downloads/

Add the folder path to env variable so they can be accessed via CLI
open powershell

`sysdm.cpl`

click on the *advanced* tab
select *path* from under *system variables* and select edit
click new and add path of sysinternals folder

Now you can use any tool from any location
Test open procmon: `procmon`
## Sigcheck

Check for unsigned files in C:\Windows\System32
`sigcheck -u -e C:\Windows\System32`

### TCPView
Show detailed listings of all TCP and UDP endpoints on the system
`tcpview -accepteula`

click on the green flag on the tool bar to display further filters for states

To view all established connections, deselect "listen" in the states filters and activate only TCP v4 and TCP v6.

## Autoruns
Identify all processes configured during system bootup or login. Find malicious processes used for persistence. 
