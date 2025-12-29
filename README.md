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

## Installation

This is a Claude Code skill. To use it:

1. Place in your skills directory: `~/.claude/skills/using-claude-code-cli/`
2. Claude Code will automatically discover and use it when relevant

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
