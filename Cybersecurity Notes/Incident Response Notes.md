### **Commands**
Commands useful for incident response on Linux based systems
	lastlog

- Tells you previously logged in users

	ps -aef –forest

- Tree of all processes running on the system (check for weird stuff) UID =  user running program, PID = process ID 

	kill PID

- Kills the given PID (Double check if it was terminated)

	who 
	w

- Check who is on the system

	ps aux | grep pts

- See who is ssh into your system

	cat /var/www/html/index.html

- See web files and look at what parts of code might be allowing access to hackers

	cd /var/log

- See logs and cat those logs to see all the things

	systemctl start [SERVICE]

- Start a service

	ps -aef --forest | awk '!/Nov/ {print}'

- Show running processes, filtered to processes started today

	lastlog | awk '/Nov/ {print}'

- Show recent logins, filtered to this month

	cat /etc/passwd | awk -F: '{ print $1}' /etc/passwd | sort

- Show all users, sorted

	find / -name "*[string]*" 2>&1 | grep -v "node-red"

- Finds all matches with that string, useful for finding hidden files/malware/logs.

	cd /home/ select a user and CHECK THEIR BASH HISTORY

  
  

Helpful list of Linux commands to check if hacked:

[https://linuxhint.com/detect_linux_system_hacked/](https://linuxhint.com/detect_linux_system_hacked/)

  

Logs:

!!!!!/var/log/auth.log or /var/log/secure (CentOS)!!!!!

- Investigate failed login attempts
    
- Investigate brute-force attacks and other vulnerabilities related to user authorization mechanism.
    
- This can be checked with sudo tail -n 50 /var/log/auth.log
    

  

!!!!!!!/var/log/faillog!!!!!!!

**

**

- It can be a useful log file to find out any attempted security breaches involving username/password hacking and brute-force attacks.
    

  

/var/log/cron

- Whenever a cron job runs, this log file records all relevant information including successful execution and error messages in case of failures.
    
- If you’re having problems with your scheduled cron, you need to check out this log file.
    

  

/var/log/yum.log

- Track the installation of system components and software packages.
    
- Check the messages logged here to see whether a package was correctly installed or not.
    
- Helps you troubleshoot issues related to software installations.
    

  

/var/log/httpd/

- The error_log contains messages related to httpd errors such as memory issues and other system related errors.
    
- This is the place where Apache server writes events and error records encountered while processing httpd requests.
    
- If something goes wrong with the Apache webserver, check this log for diagnostic information.
    
- Besides the error-log file, Apache also maintains a separate list of access_log.
    
- All access requests received over HTTP are stored in the access_log file.
    
- Helps you keep track of every page served and every file loaded by Apache.
    
- Logs the IP address and user ID of all clients that make connection requests to the server.
    
- Stores information about the status of the access requests, – whether a response was sent successfully or the request resulted in a failure.
    

  

Directories/files

/tmp/

  

/etc/passwd

  

/etc/shadow

  
**