
# Usage (Basic Commands)  

`tmux new` - creates a new session  

Use the `-s` flag to add session name -> `tmux new -smysession`  

**Prefix key** - once attached to a tmux session, prefix key can be used to execute tmux commands. Default is `C-b`  

Use `tmux attach -tmysession` to attach to an existing named session. Additional `-d` flag can be used to detached all attached clients  

To create and directly attach to a session use the command `tmux new -Amysession`  

Use `tmux ls` to list down the available sessions. When attaced to a client, using `C-b s` shows the list of active sessions  

To create a new window inside an attached seesion, use `C-b c`
