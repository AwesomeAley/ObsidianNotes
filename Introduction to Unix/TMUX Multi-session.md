The `tmux` command, short for terminal multiplexer, allows for multiple terminals to be opened and viewed on the same screen. 

In this step, you will start a `tmux` session, using the `new-session` option, and run the `top` command in the current `tmux` session:

	tmux new-session 'top'

Detach from the current `tmux` session, which is running the `top` command, by pressing the **Ctrl**+**B** key sequence and then the **D** key to return to the shell prompt again:

	**CTRL**+**b**
	d

Confirm that `tmux` session `0` still exists by executing the following command:

	tmux ls

To re-attach the running `tmux` session `0`, use the `tmux attach` command with the target-session `-t` flag:

	tmux attach -t 0

To enable a new terminal in the `tmux` session running in a side-by-side vertical window, press **Ctrl**+**B** then **%** (**Ctrl** and **b**, then **Shift**+**5**):

	Ctrl+b
	%




