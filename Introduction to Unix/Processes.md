#### Process related Commands
ps- command can be used to list processes
	aux - flag that shows user owners
watch - monitor processes (ctrl-c to end command)
jobs - display running background processes
fg - send background process back to the foreground
bg - send the process back to the foreground
free- display basic memory statistics
uptime - basic process information

To execute the script in the background, add an ampersand `&` character at the end of the command:

A user can influence the priority that will be assigned to a process by setting a value of something called niceness. The higher the niceness value, the lower the priority that will be assigned to a process.

To set the initial niceness of a command, use the `nice` command as a prefix to the command to execute. The `-n` option indicates the desired niceness value.

Start the `sleep` command with a lower priority and then confirm with the `-l` option to the `ps` command:

	su - root
	nice -n 10 sleep 200 &
	ps -l