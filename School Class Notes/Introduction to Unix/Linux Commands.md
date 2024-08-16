A list of commands used in the CLI of Linux/Unix
Commands below are general commands, but commands to know also include
Commands for [[Linux File Creation and Manipulation]]

``` ascii
tag of "&" will make a program run in the background
```

**System processes**
ps - list processes for current user running on the system
	ps aux - list all processes 
top - real time statistics on processes
kill (PID of process) - end a process
	- SIGTERM - Kill the process, but allow it to do some cleanup tasks beforehand
- SIGKILL - Kill the process - doesn't do any cleanup after the fact
- SIGSTOP - Stop/suspend a process

Enter the use of `systemctl` -- this command allows us to interact with the **systemd** process/daemon. Continuing on with our example, systemctl is an easy to use command that takes the following formatting: `systemctl [option] [service]`

For example, to tell apache to start up, we'll use `systemctl start apache2`. Seems simple enough, right? Same with if we wanted to stop apache, we'd just replace the `[option]` with stop (instead of start like we provided)

We can do four options with `systemctl`:

- Start
- Stop
- Enable 
- Disable

**Filesystem Navigation**
cd - change directory
ls - list contents in directory
	-a/--all : lists all files in directory
	-l : shows the listing in long format
pwd - print working directory (display current directory)


clear - clears terminal
whoami - displays current user in use
cat - concatenate a file (run the file)
sudo - temporarily increase your privileges to root privileges
echo - repeats what is typed after
touch - create file
rm - delete file
mkdir - make directory
rmdir - delete directory
chmod - change permissions
cp (source file) (destination file) - copies information from one file to another
man - get information from the manual on commands
find/locate - locates path to specified file
whereis - finds source files for a command
type - determines information about various commands
watch - monitor processes