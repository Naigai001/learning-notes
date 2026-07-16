# tmux Basics

Short notes for daily terminal multiplexing.

## Sessions

```bash
tmux                    # start a new session
tmux new -s work        # named session
tmux ls                 # list sessions
tmux attach -t work     # attach
tmux attach             # attach last
# inside tmux: Ctrl-b d  detach
tmux kill-session -t work
```

## Windows

Prefix is `Ctrl-b` by default.

| Action | Keys |
|---|---|
| New window | `Ctrl-b c` |
| Next / previous | `Ctrl-b n` / `Ctrl-b p` |
| Select by number | `Ctrl-b 0..9` |
| Rename window | `Ctrl-b ,` |
| Close window | `Ctrl-b &` |

## Panes

| Action | Keys |
|---|---|
| Split horizontal | `Ctrl-b "` |
| Split vertical | `Ctrl-b %` |
| Move between panes | `Ctrl-b` + arrow / `o` |
| Zoom pane | `Ctrl-b z` |
| Close pane | `Ctrl-b x` |
| Resize pane | `Ctrl-b` + hold arrow |

## Quick reference

```bash
# create work session with two panes
tmux new -s work -d
tmux split-window -h -t work
tmux attach -t work
```

## Tips

- Detach instead of killing long-running jobs
- Name sessions by project (`work`, `ops`, `logs`)
- Prefer zoom (`Ctrl-b z`) over closing panes when you need temporary focus
- Keep a simple `~/.tmux.conf` for mouse and history-limit if needed
