---
name: install-skill-creator
description: Install the skill-creator skill from the Anthropic plugins marketplace
---

## Add the Marketplace Source

Run the following command in Claude Code to register the Anthropic skills marketplace:

```bash
/plugin marketplace add anthropics/skills
```

## Install the Skill

Then install the skill-creator skill from the registered source:

```bash
/plugin install skill-creator@anthropic-agent-skills
```
