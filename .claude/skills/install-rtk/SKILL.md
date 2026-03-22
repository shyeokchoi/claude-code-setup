---
name: install-rtk
description: Install RTK (Rust Token Killer), a CLI proxy that reduces Claude Code token usage by 60–90%
---

## Install

```bash
brew install rtk
```

## Verify Installation

```bash
rtk --version   # Should show the installed version (e.g., "rtk 0.28.2")
rtk gain        # Should display token savings stats
```

## Set Up the Claude Code Hook

RTK works by intercepting CLI commands (e.g., `git status`) and returning token-optimized output. To enable this, register RTK as a Claude Code hook:

```bash
# Install the hook globally for Claude Code
rtk init --global
# Follow the on-screen instructions to register in ~/.claude/settings.json
# Targets Claude Code by default (use --opencode for OpenCode, --gemini for Gemini CLI)
```

After setup, restart Claude Code. Commands like `git status` will automatically be rewritten to `rtk git status`.
