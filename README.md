# Custom Prompts Collection

## Project Overview

This repository provides a collection of production-ready prompt configurations for various AI assistants, specifically designed for [tprompts](https://github.com/thongntit/tprompts) compatibility. Each prompt collection includes system instructions, custom commands, and specialized workflows optimized for different use cases including coding assistance, productivity management, and knowledge organization.

## Quick Start

Install [tprompts](https://github.com/thongntit/tprompts):

```bash
npm install -g @thongntit/tprompts
```

Then install prompts directly from this repository using the examples below.

## Available Prompts

### 1. AI Coding Agent (Claude Code)
Enhanced coding assistant with memory management and workflow automation.

📖 [View detailed documentation](./prompts/coding-agent/README.md)

```bash
tprompts install https://github.com/thongntit/prompts.git/prompts/coding-agent claude-code
```

---

### 2. Obsidian Monthly Planner (Claude Code)
Monthly planning and goal tracking for Obsidian vaults with PARA methodology integration.

📖 [View detailed documentation](./prompts/obsidian-monthly-planner/README.md)

```bash
tprompts install https://github.com/thongntit/prompts.git/prompts/obsidian-monthly-planner claude-code
```

---

## Repository Structure

```
prompts/
├── coding-agent/              # Claude Code: General coding assistant
│   ├── system-prompt.md       # Global coding guidelines
│   ├── commands/              # Custom slash commands
│   └── tprompts.json          # Configuration
└── obsidian-monthly-planner/  # Claude Code: Monthly planning
    ├── .claude/commands/      # Monthly planner command
    └── tprompts.json          # Configuration
```

## Recent Updates

- **January 2025**: Restructured all prompts for tprompts compatibility
- Added README files with installation instructions for each prompt collection
- Implemented Obsidian Second Brain workflow with PARA methodology
- Added context extraction/loading workflows for conversation management
- Integrated Vibe Designer functionality into coding-agent commands

## Contributing

Contributions are welcome! When adding new prompts:

1. Follow the tprompts structure with `tprompts.json` configuration
2. Include a detailed README.md with installation instructions
3. Document all custom commands and their usage
4. Test with the target editor (Claude Code, Roo Code, etc.)
