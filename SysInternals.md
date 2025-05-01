## Initial Setup
Download tools or the entire suite from https://learn.microsoft.com/en-us/sysinternals/downloads/

Add the folder path to env variable so they can be accessed via CLI
open powershell

`sysdm.cpl`

click on the *advanced* tab
select *path* from under *system variables* and select edit
click new and add path of sysinternals folder

## Sigcheck

Check for unsigned files in C:\Windows\System32
`sigcheck -u -e C:\Windows\System32`



