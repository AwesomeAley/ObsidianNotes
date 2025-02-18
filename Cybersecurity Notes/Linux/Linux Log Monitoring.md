## System Log Directories
The **/var/log** directory is a repository of log files useful for event monitoring

Kernel messages
`/var/log/kern.log`
`/var/log/syslog`

Authentication events (logins)
`/var/log/auth.log`
`/var/log/btmp`: failed logins
`/var/log/wtmp`: every login and logout

## Auditd

Auditd logs are stored in **/var/log/audit/audit.log**
This can be queried with `ausearch`

Search by applied keys
`sudo ausearch -k [KEY]`

### Defining Audit Rules
Tracking changes to the /etc/passwd file
`sudo auditctl -w /etc/passwd -p wrap -k users`

Execve system calls
`sudo auditctl -a always,exit -F arch=b64 -S execve -k execve_syscalls `




