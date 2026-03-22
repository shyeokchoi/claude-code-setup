---
name: install-claude-status-line
description: Install the Claude HUD plugin, which displays a real-time status line in the terminal
---

## Add the Marketplace Source

Register the plugin source in Claude Code:

```bash
/plugin marketplace add jarrodwatts/claude-hud
```

## Install the Plugin

Install the Claude HUD plugin from the registered source:

```bash
/plugin install claude-hud
```

## Run Initial Setup

Configure the status line display:

```bash
/claude-hud:setup
```