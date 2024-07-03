# Tmux

## Session Management 

| Command                             | Description                                   |
| ----------------------------------- | --------------------------------------------- |
| tmux new -s <session_name>          | Create a new Tmux session with the given name |
| tmux attach -t <session_name>       | Attach to an existing Tmux session            |
| tmux ls                             | List all running Tmux sessions                |
| tmux kill-session -t <session_name> | Terminate the specified Tmux session          |

## Window Management 
| Command        | Description                   |
| -------------- | ----------------------------- |
| Ctrl+space c   | Create a new window           |
| Ctrl+space w   | List all windows              |
| Ctrl+space 0-9 | Switch to the window number   |
| Ctrl+space n   | Switch to the next window     |
| Ctrl+space p   | Switch to the previous window |
| Ctrl+space &   | Close the current window      |

## Pane Management 
| Command      | Description                         |
| ------------ | ----------------------------------- |
| Ctrl+space " | Split the current pane horizontally |
| Ctrl+space % | Split the current pane vertically   |
| Ctrl+space o | Switch to the next pane             |
| Ctrl+space ; | Switch to the previous pane         |
| Ctrl+space x | Close the current pane              |
| Ctrl+space z | Toggle pane zoom                    |

## Other Useful Commands 
| Command      | Description                                           |
| --------     | ----------------------------------------------------- |
| Ctrl+space d | Detach from the current Tmux session                  |
| Ctrl+space ? | Display the Tmux command cheatsheet                   |
| Ctrl+space : | Enter the Tmux command prompt                         |
| Ctrl+space [ | Enter copy mode to scroll through the terminal output |
| Ctrl+space ] | Paste the most recent copy                            |

## Copy Mode
| Command           | Description   |
| ----------------- | ------------- |
| move character    | j k h l       |
| move line         | Ctrl+Y Ctrl+E |
| move whole screen | Ctrl+B Ctrl+F |
| search            | /             |
| start selection   | Space         |
| copy selection    | Enter         |
| clear selection   | Escape        |
| exit copy mode    | q             |

## [Tmux Resurrect](https://github.com/tmux-plugins/tmux-resurrect)
| Command           | Description                |
| ----------------- | -------------------------- |
| Ctrl+space Ctrl+s | Save current session       |
| Ctrl+space Ctrl+r | Restore last saved session |

## [Tmux Yank](https://github.com/tmux-plugins/tmux-yank)
| Command                    | Description                                         |
| -------------------------- | --------------------------------------------------- |
| (normal mode) Ctrl+space y | Copies text from the commmand line to the clipboard |
| (normal mode) Ctrl+space Y | Copy the PWD to the clipboard                       |
| (copy mode) y              | Copy selection to system clipboard                  |
| (copy mode) Y              | Put selection to the command line                   |

## [Tmux Copycat](https://github.com/tmux-plugins/tmux-copycat)
| Command         | Description                                                         |
| --------------- | ------------------------------------------------------------------- |
| prefix + /      | Regex search                                                        |
| prefix + ctrl+f | Simple file search                                                  |
| prefix + ctrl+g | Jumping over git status files (best used after git status command)  |
| prefix + alt+h  | Jumping over SHA-1/SHA-256 hashes (best used after git log command) |
| prefix + ctrl+u | Url search (http, ftp and git urls)                                 |
| prefix + ctrl-d | Number search (mnemonic d, as digit)                                |
| prefix + alt-i  | Ip address search                                                   |
| (copy mode) n   | Jumps to the next match                                             |
| (copy mode) N   | Jumps to the previous match                                         |

