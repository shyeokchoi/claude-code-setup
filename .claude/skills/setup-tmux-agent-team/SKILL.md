---
name: setup-tmux-agent-team
description: Set up tmux and enable Claude Code Agent Team with split-pane mode
---

## Install tmux

```bash
brew install tmux
```

## Configure tmux

Add the following to `~/.tmux.conf` (create the file if it doesn't exist):

```
# Enable mouse support (required for pane switching, resizing, and scrolling)
set -g mouse on

# Increase scroll buffer (default 2000 → 10000 recommended for verbose agent output)
set -g history-limit 10000

# Enable iTerm2 native scrollback (trackpad/mouse wheel scrolling in iTerm2)
set -g terminal-overrides 'xterm*:smcup@:rmcup@'
```

## Enable Agent Team in Claude Code

Add the following environment variables to `~/.claude/settings.json` inside the `env` object:

```json
"CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1",
"CLAUDE_CODE_AGENT_TEAM_MODE": "split-pane"
```

## Grant tmux Permission

Add the following to `~/.claude/settings.json` inside `permissions.allow`:

```json
"Bash(tmux:*)"
```
