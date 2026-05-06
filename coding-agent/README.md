# Coding Agent

Coding assistant rules and workflow commands for Claude Code, distributed as a plugin.

## What you get

- **`coding-agent` skill** — global rules covering code quality, memory/context management, planning, and decision-making (loads contextually when relevant)
- **Commands**:
  - `/vibe-designer` — design and define the vibe/style of your project
  - `/load-context` — load conversation context from `windsurf.md` files
  - `/web-search` — perform web searches within the coding session
  - `/extract-context` — extract and save conversation context to `windsurf.md` files

## Install

```bash
/plugin marketplace add thongntit/prompts
/plugin install coding-agent@thongntit-prompts
```
