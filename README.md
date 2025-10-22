# Custom Prompts for AI Coding Assistants

## Project Overview

This repository provides a collection of production-ready prompt configurations for AI coding assistants, specifically designed for [tprompts](https://github.com/dzhng/tprompts) compatibility. Each prompt collection includes system instructions, custom commands, and specialized workflows optimized for different coding and productivity scenarios.

## Quick Start

Install [tprompts](https://github.com/dzhng/tprompts) and register this repository:

```bash
# Install tprompts
npm install -g tprompts

# Register this repository
tprompts register https://github.com/thongntit/prompts.git
```

## Available Prompts

### 1. AI Coding Agent (Claude Code)
**Purpose**: Enhanced coding assistant with memory management and workflow automation

```bash
tprompts install prompts/coding-agent claude-code
```

**Features:**
- Global coding guidelines and best practices
- Context extraction and loading via windsurf.md files
- Web search integration
- Vibe designer for project styling

**Commands:** `/vibe-designer`, `/load-context`, `/extract-context`, `/web-search`

---

### 2. Obsidian Agent (Claude Code)
**Purpose**: Productivity assistant for Obsidian vault management

```bash
tprompts install prompts/obsidian-agent claude-code
```

**Features:**
- PARA methodology (Projects, Areas, Resources, Archives)
- Task tracking and management
- Calendar integration
- Vault organization automation

**Commands:** Available as `/obsidian-agent`

---

### 3. Obsidian Second Brain (Roo Code)
**Purpose**: Custom Roo Code mode for personal knowledge management

```bash
tprompts install prompts/obisidian-second-brain roo
```

**Features:**
- PARA methodology implementation
- Weekly and monthly review workflows
- Memory system updates
- Planning automation

**Commands:** `/weekly-review`, `/monthly-review`, `/weekly-planner`, `/update-memory`

---

## Repository Structure

```
prompts/
├── coding-agent/          # Claude Code: General coding assistant
│   ├── system-prompt.md   # Global coding guidelines
│   ├── commands/          # Custom slash commands
│   └── tprompts.json      # Configuration
├── obsidian-agent/        # Claude Code: Obsidian productivity
│   ├── agent-instructions # PARA methodology instructions
│   └── tprompts.json      # Configuration
└── obisidian-second-brain/ # Roo Code: Knowledge management
    ├── .roo/commands/     # Productivity commands
    └── tprompts.json      # Configuration
```

## Direct Installation

Each prompt can also be installed directly without repository registration:

```bash
# Example for coding-agent
tprompts install https://github.com/thongntit/prompts/tree/main/prompts/coding-agent claude-code
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

## License

This repository contains custom prompt configurations for personal and professional use.