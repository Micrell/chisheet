---
tags:
  - keybind
---

## Commands out session 
```sh
#List sessions
tmux ls
#New session
tmux new -s <session_name>
#Attach session
tmux attach -t <session_name>
#Detach the current session
tmux detach
```
If the last pane off the session is killed, the session is killed so it will not be seen in 'tmux ls' anymore.

## Commands in session

prefix (P) -> ctrl + b

| command                    | action            |
| -------------------------- | ----------------- |
| P + s                      | list sessions     |
| P + w                      | list window       |
| P + %                      | split vertical    |
| P + "                      | split horizontal  |
| P + ⬆️\|⬇\|⬅\|➡️           | nav win           |
| P + c                      | create window     |
| P + ,                      | rename window     |
| P + &                      | kill window       |
| P + [                      | enter scroll mode |
| scroll mode + ctrl + space | start selection   |
| scroll mode + ctrl + w     | copy selection    |

Enter a command -> P + :

synchronize panes -> setw synchronise-panes
desynchronize panes -> setw synchronise-panes off