The `ps` command is used when you want to view information about processes running on a Unix/Linux system. It is essential for managing system resources, diagnosing issues, and understanding system behavior.

The `ps` command can be used without any options to list processes that belong to the current user and are associated with the terminal where the command is run.

**Parameters (flags):**
`-A` display information on all processes running on the system
`-a` displays processes from all users
`i`
`-f` display additional information on processes

The trick is to pipe the command into grep to look for specific processes
