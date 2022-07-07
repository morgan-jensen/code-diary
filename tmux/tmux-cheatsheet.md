# Tmux Cheat Sheet

Ref:
Lines starting with `$` are bash commands  
Lines starting with `:` are tmux commands (`Ctrl+b` `:` to enter command mode)  
Lines starting with `cmd` are commands that follow a press of `Ctrl + b`)
    - Ex: `cmd c` = `Ctrl + b` then `c`


## Sessions
Creating:
* `$ tmux` or `$ tmux new`: Start a new session 
        * `:new`
* `$ tmux new -s mysession`: Start a new session with the name __mysession__
        * `:new -s mysession`

Destroying:
* `$ tmux kill-session -t mysession`: Kill / Delete session __mysession__ 
* `$ tmux kill-session -a`: Kill all sessions except the current
* `$ tmux kill-session -a -t mysession`: Kill all sessions by __mysession__

Attaching:
* `$ tmux a`: Attach to last session
* `$ tmux a -t mysession`: Attach to session with name __mysession__

List Sessions:
* `$ tmux ls`: Show all sessions
* `cmd s`: Show all sessions

Other:
* `cmd $`: Rename session
* `cmd d`: Detach from session
* `cmd w`: Session and Window Preview
* `cmd (`: Move to previous session
* `cmd )`: Move to next session

## Windows
* `$ tmux new -s mysession -n mywindow`: Start a new session called __mysession__ and window __mywindow__
* `cmd c`: Create window
* `cmd ,`: Rename window 
* `cmd &`: Close current window
* `cmd p`: Previous window
* `cmd n`: Next window
* `cmd [0...9]`: Switch to window by number
* `cmd l`: Toggle last active window

* `:swap-window -s 2 -t 1`: Reorder window '-s' = src, -t = dst 
* `:swap-window -t -1`: Move window to the left by one position

## Panes
* `cmd ;`: Toggle last active pane 
* `cmd %`: Split pane horizontally 
* `cmd "`: Split pane vertically
* `cmd {`: Move the current pane left
* `cmd }`: Move the current pane right
* `cmd [up, down, left, right]`: Switch to pane
* `cmd q`: Show pane numbers
* `cmd q [0...9]`: Switch to pane by number
* `cmd z`: Toggle pane zoom
* `cmd !`: Convert pane into a window 
* `cmd Ctrl + [up, down, left, right]`: Adjust pane size
* `cmd x`: Close current pane 
* `cmd Spacebar`: Toggle between pane layouts
* `cmd o`: Switch to next pane 

## Misc
* `cmd ?`: List shortcuts
* `$ tmux info`: Show everything
