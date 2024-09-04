
## Commands out session 

```sh
#List sessions
tmux ls
#New session
tmux new -s <session_name>
#Attach session
tmux attach -t <session_name>
```

```ad-warning
If the last pane off the session is killed, the session is killed so it will not be seen in 'tmux ls' anymore.
```
## Commands in session

prefix (P) -> ctrl + a || ctrl + b
list sessions -> P + s
list window -> P + w
split vertical -> P + -
split horizontal -> P + _
nav win -> P + ⬆️|⬇|⬅|➡️
create window -> P + c
rename window -> P + ,
kill window -> P + &

Enter a command -> P + :

synchronize panes -> setw synchronise-panes
desynchronize panes -> setw synchronise-panes off

```sh
#Detach the current session
tmux detach
```
