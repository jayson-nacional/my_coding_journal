
# TMUX  

Is a program that runs in a terminal and allows other terminal programs to be run inside it.  

Tmux keeps all its state in a single main process called the `tmux server`  

- Programs run in terminals in panes, which each belong to one window
- Each window has a name and one active pane
- Windows are linked to one or more sessions
- Each session has a list of windows, each with an index
- One of the windows in the current session is the current window
- Sessions are attached to one or more clients, or are detached (attached to no clients)
- Each client is attached to one session  

|   Term    |   Description |
|   ---     |   ---     |
|   Client  |   Attaches a tmux session from an outside terminal such as xterm(1)   |
|   Session |   Groups one or more windows together |
|   Window  |   Groups one or more panes together, linked to one or more sessions   |
|   Pane    |   Contains a terminal and running program, appears in one window  |
|   Active Pane |   The pane in the current window where the typing is sent; one per session    |
|   Current Window  |   The window is the attached session where typing is sent; one per session    |
|   Last Window |   The previous current window |
|   Session name    |   The name of a session, defaults to a number starting from 0 |
|   Window list    |   The list of windows in a session in order by number |
|   Window name |   The name of a window, defaults to the name of the running program in the active pane    |
|   Window index    |   The number of a window in a session's window list   |
|   Window layout   | The size and position of the panes in a window    |
