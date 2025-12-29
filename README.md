# Using Claude Code CLI

A Claude Code skill for programmatically invoking Claude Code CLI from Python orchestrators, shell scripts, and automation pipelines.

## Overview

This skill provides comprehensive patterns for:

- **Tool Pre-Approval** — Eliminate permission prompts with `--allowedTools`
- **Directory Access** — Grant Claude access to additional directories with `--add-dir`
- **Hooks Configuration** — Set up logging, monitoring, and blocking hooks
- **Sandbox Mode** — Safe execution for untrusted operations
- **Python Patterns** — Synchronous, async, and parallel subprocess invocation
- **JSON Extraction** — Parse structured output from CLI responses
- **Fallback Strategies** — OpenCode CLI as backup

## Quick Start

```bash
# Minimal automation command
claude -p "Your prompt" --allowedTools Write Read Edit

# Full automation with all options
claude \
  --model sonnet \
  --add-dir /path/to/skills \
  --allowedTools Write Read Edit Bash Task \
  --output-format json \
  -p "Your automation prompt"
```

## File Structure

```
using-claude-code-cli/
├── SKILL.md                           # Main skill document
├── README.md                          # This file
├── .gitignore                         # Git ignore patterns
└── references/
    ├── cli-reference.md               # Complete CLI commands and flags
    ├── subprocess-patterns.md         # Python invocation patterns
    ├── hooks-examples.md              # Hook configuration and scripts
    ├── json-extraction.md             # Parsing JSON from output
    └── orchestrator_example.py        # Complete Python orchestrator class
```

## Installing with Skilz (Universal Installer)

The recommended way to install this skill across different AI coding agents is using the **skilz** universal installer.

### Install Skilz

```bash
pip install skilz
```

This skill supports [Agent Skill Standard](https://agentskills.io/) which means it supports 14 plus coding agents including Claude Code, OpenAI Codex, Cursor and Gemini.


### Git URL Options

You can use either `-g` or `--git` with HTTPS or SSH URLs:

```bash
# HTTPS URL
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill

# SSH URL
skilz install --git git@github.com:SpillwaveSolutions/using-claude-code-cli-agent-skill.git
```

### Claude Code

Install to user home (available in all projects):
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill
```

Install to current project only:
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --project
```

### OpenCode

Install for [OpenCode](https://opencode.ai):
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --agent opencode
```

Project-level install:
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --project --agent opencode
```

### Gemini

Project-level install for Gemini:
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --agent gemini
```

### OpenAI Codex

Install for OpenAI Codex:
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --agent codex
```

Project-level install:
```bash
skilz install -g https://github.com/SpillwaveSolutions/using-claude-code-cli-agent-skill --project --agent codex
```


### Install from Skillzwave Marketplace
```bash
# Claude to user home dir ~/.claude/skills
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli

# Claude skill in project folder ./claude/skills
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli --project

# OpenCode install to user home dir ~/.config/opencode/skills
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli --agent opencode

# OpenCode project level
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli --agent opencode --project

# OpenAI Codex install to user home dir ~/.codex/skills
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli

# OpenAI Codex project level ./.codex/skills
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli --agent opencode --project


# Gemini CLI (project level) -- only works with project level
skilz install SpillwaveSolutions_using-claude-code-cli-agent-skill/using-claude-code-cli --agent gemini

```

See this site [skill Listing](https://skillzwave.ai/skill/SpillwaveSolutions__using-claude-code-cli-agent-skill__using-claude-code-cli__SKILL/) to see how to install this exact skill to 14+ different coding agents.


### Other Supported Agents

Skilz supports 14+ coding agents including Windsurf, Qwen Code, Aidr, and more.

For the full list of supported platforms, visit [SkillzWave.ai/platforms](https://skillzwave.ai/platforms/) or see the [skilz-cli GitHub repository](https://github.com/SpillwaveSolutions/skilz-cli)


<a href="https://skillzwave.ai/">Largest Agentic Marketplace for AI Agent Skills</a> and
<a href="https://spillwave.com/">SpillWave: Leaders in AI Agent Development.</a>

## Triggers

The skill activates on queries containing:
- "claude cli", "claude subprocess", "claude permissions"
- "--allowedTools", "--add-dir", "--settings"
- "spawn claude", "headless claude", "parallel agents"

## Use Cases

| Scenario | Reference |
|----------|-----------|
| Python subprocess invocation | [subprocess-patterns.md](references/subprocess-patterns.md) |
| Setting up hooks for logging | [hooks-examples.md](references/hooks-examples.md) |
| Parsing JSON from output | [json-extraction.md](references/json-extraction.md) |
| Complete orchestrator class | [orchestrator_example.py](references/orchestrator_example.py) |
| CLI flag reference | [cli-reference.md](references/cli-reference.md) |

## License

MIT
