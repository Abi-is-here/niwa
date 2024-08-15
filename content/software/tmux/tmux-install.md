---
 title: 
 date created: 
 date modified: 
 tags:
 - software
---

## Install tmux

`sudo apt install tmux`

## Install plugins

`git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`

[More info here](https://github.com/tmux-plugins/tpm)

## Dotfile

```bash title=".tmux.conf"
set-option -g prefix C-a
bind-key C-a send-prefix
# split panes using | and -
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %
# reload config file (change file location to your the tmux.conf you want to use)
bind r source-file ~/.tmux.conf \; display-message "~/.tmux.conf reloaded."
# switch panes using Alt-arrow without prefix
bind -n M-Left select-pane -L
bind -n M-Right select-pane -R
bind -n M-Up select-pane -U
bind -n M-Down select-pane -D
# Enable mouse control (clickable windows, panes, resizable panes)
set -g mouse on
# default window title colors

if-shell "test '\( #{$TMUX_VERSION_MAJOR} -eq 2 -a #{$TMUX_VERSION_MINOR} -ge 6 \)'" 'set -g default-terminal "xterm-256color"'
if-shell "test '\( #{$TMUX_VERSION_MAJOR} -eq 2 -a #{$TMUX_VERSION_MINOR} -ge 6 \)'" 'set -ga terminal-overrides ",xterm-256color:Tc"'

if-shell '\( #{$TMUX_VERSION_MAJOR} -eq 2 -a #{$TMUX_VERSION_MINOR} -lt 6\) -o #{$TMUX_VERSION_MAJOR} -le 1' 'set -g default-terminal "xterm-256color"'


set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'Nybkox/tmux-kanagawa'
set -g @kanagawa-plugins "cpu-usage ram-usage time"

run '~/.tmux/plugins/tpm/tpm'
```
