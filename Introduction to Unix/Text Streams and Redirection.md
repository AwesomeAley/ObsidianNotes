[[Linux Commands]] that can be used for data redirection

#### Data Redirection Characters:

(>) - directs input into file and **replaces**
(>>) - directs input into file and **appends**
(tee) - directs input both to command line and file (overwrites ( to append add -a flag))

(2>&1) / (&>) - direct both the input and the output into a file
(|) - command pipeline is used to send the output of one command to another

(xargs) - command is used to read data from standard input and execute a command based on the input
	ex: echo 'x1 x2 x3 x4' | xargs touch = will create 4 files with those names