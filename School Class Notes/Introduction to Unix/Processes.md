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

#### Multi - Sessions
Multi-session command line utilities allow users to manage multiple processes inside a single Bash shell environment. The `screen` and `tmux` commands allow the user to start processes in a session that can be detached while still running, then re-attached and managed by various methods.

[[TMUX Multi-session]] can be used to run multiple processes that can be viewed at the same time

The `screen` command allows for multiple processes to run within separate sessions under a single terminal.

A useful feature of the `screen` command is the ability to detach a session, then re-attach it later. To attach and detach a `screen` session, you will need to use the `screen` command keys. All `screen` commands start with a prefix key, the keystrokes **Ctrl**+**A**, followed by a command key to make an action happen.

Press the prefix key **Ctrl**+**A** and then the detach **D** command key, which detaches the current `screen` session and returns the user to the shell prompt.

To list currently running `screen` sessions, run the `screen` command with the list `-list` option:

	screen -list

You can now re-attach the session by using the resume `-r` option with either the PID of the session or by the name of the session:

	screen -r PID

To exit the `screen` command, use the `exit` command:

	exit