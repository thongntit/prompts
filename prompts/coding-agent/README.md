# AI Coding Agent

Global rules for AI coding assistant with memory and context management, plus workflow commands.

## Installation

Install this prompt using [tprompts](https://github.com/thongntit/tprompts):

```bash
# Direct installation (no registration required)
tprompts install https://github.com/thongntit/prompts/tree/main/prompts/coding-agent claude-code
```

Or register the repository first for easier management:

```bash
# Register the repository
tprompts register https://github.com/thongntit/prompts.git

# Then install the prompt
tprompts install prompts/coding-agent claude-code
```

## Features

- **System Prompt**: Global coding guidelines and best practices for Claude Code
- **Custom Commands**:
  - `/vibe-designer` - Design and define the vibe/style of your project
  - `/load-context` - Load conversation context from windsurf.md files
  - `/web-search` - Perform web searches within the coding session
  - `/extract-context` - Extract and save conversation context to windsurf.md files

## Editor Support

- **Claude Code**: System prompt and custom commands

## Usage

After installation, the system prompt will be automatically loaded in Claude Code, and the custom commands will be available via slash commands.
