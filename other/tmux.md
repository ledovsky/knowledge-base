# Tmux

## Мой подход к использованию

У tmux есть несколько сценариев использования. Некоторые используют его, как IDE для VIM. Кто-то использует его для организации системного администрирования серверов. Я использую tmux для работы на личном компьютере, для поддержания persistance рабочих процессов, заменяя вкладки терминала.

Мой подход минималистичен. Поэтому я не исопользую окна (windows). Одна сессия (session) соответствует одной задаче. В каждой сессии обычно не больше двух панелей (panes). Чаще всего одна.

## Команды и сокращения

Управление сессиями. Рекомендуется использовать только именованные сессии.

    tmux new -s session_name - new session
    tmux a -t session_name - attach
    tmux kill-session -t session_name - kill session
    tmux ls - list sessions

    Ctrl-a - prefix (мой ребинд)
    Ctrl-b - стандартный prefix

    d - detach
    r - reload config (мой ребинд)

Использование панелей (panes)

    Стандартные команды
    % - new pane left
    " - new pane down
    x - kill pane
    up, down, left, right - move

    Мой ребинд
    v - vertical split
    s - horizontal split
    hjkl - move
    HJKL - change pane size

## Конфигурация

Находится в `~/.tmux.conf`

```bash
# Config: Alexander Ledovsky
# Based on lots of different pieces found

# Default termtype. If the rcfile sets $TERM, that overrides this value.
set -g default-terminal screen-256color

# Keep your finger on ctrl, or don't
bind-key ^D detach-client

# Create splits and vertical splits
bind-key v split-window -h -p 50 -c "#{pane_current_path}"
bind-key s split-window -p 50 -c "#{pane_current_path}"

# Pane resize in all four directions using vi bindings.
# Can use these raw but I map them to shift-ctrl-<h,j,k,l> in iTerm.
bind -r H resize-pane -L 5
bind -r J resize-pane -D 5
bind -r K resize-pane -U 5
bind -r L resize-pane -R 5

# VIM-like bindings to switch panes
unbind l
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# set first window to index 1 (not 0) to map more to the keyboard layout...
set-option -g base-index 1
set-window-option -g pane-base-index 1

# Patch for OS X pbpaste and pbcopy under tmux.
set-option -g default-command "which reattach-to-user-namespace > /dev/null && reattach-to-user-namespace -l $SHELL || $SHELL"

# Screen like binding
unbind C-b
set -g prefix C-a
bind a send-prefix

# No escape time for vi mode
set -sg escape-time 0

# Bigger history
set -g history-limit 10000

# force a reload of the config file
unbind r
bind r source-file ~/.tmux.conf \; display "Reloaded!"

# VIM keybindings - to learn
# Use vi keybindings for tmux commandline input.
# Note that to get command mode you need to hit ESC twice...
set -g status-keys vi

# Use vi keybindings in copy and choice modes
setw -g mode-keys vi
```
