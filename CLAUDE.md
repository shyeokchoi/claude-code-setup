# Setup Instructions

Set up the following development environment using the skills in this repository.

### RTK
A token-saving CLI proxy that reduces token usage by 60–90% on common dev operations (e.g., `git status`, `git diff`). It rewrites CLI commands transparently via a Claude Code hook.

### Superpowers
A structured development workflow plugin that provides 14 skills for planning, TDD, systematic debugging, code review, git worktree management, parallel agent dispatch, and more.

### Skill Creator
A skill for creating new Claude Code skills. Useful for authoring and packaging your own custom skills.

### Status Line
Displays a real-time status line in the terminal showing Claude Code session info such as model, mode, token usage, and cost.

### tmux + Agent Team
Installs tmux and enables Claude Code's Agent Team feature in split-pane mode, allowing agents to work in parallel across tmux panes.

### Set Default Mode to "Plan"
No skill is needed for this — just edit `~/.claude/settings.json` directly and add the following option:

This makes Claude Code start in plan mode by default, so it proposes changes before executing them.

```json
"permissions": {
  "defaultMode": "plan"
}
```

### Set Default attribution to empty string
No skill is needed for this — just edit `~/.claude/settings.json` directly and add the following option or edit the current option:

```json
"attribution": {
  "commit": "",
  "pr": ""
}
```

### Enable Notifications
Sends a macOS notification when Claude Code needs your attention (e.g., waiting for approval or asking a question).

First, install `terminal-notifier`:

```bash
brew install terminal-notifier
```

Then add the following hook to `~/.claude/settings.json` inside the `hooks` object:

```json
"Notification": [
  {
    "matcher": "",
    "hooks": [
      {
        "type": "command",
        "command": "terminal-notifier -title 'Claude Code' -message 'Claude Code needs your attention'"
      }
    ]
  }
]
```

