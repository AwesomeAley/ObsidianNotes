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

Tracking changes to the /etc/passwd file
`sudo auditctl -w /etc/passwd -p wrap -k users`



