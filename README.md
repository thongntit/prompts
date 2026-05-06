# thongntit-prompts

A Claude Code [plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces) with two plugins.

## Plugins

| Plugin | Description |
| :----- | :---------- |
| [`coding-agent`](./coding-agent/README.md) | Coding assistant rules + workflow commands (`/vibe-designer`, `/load-context`, `/web-search`, `/extract-context`) |
| [`obsidian-second-brain`](./obsidian-second-brain/README.md) | Obsidian PARA workflow as 9 auto-invoked skills: `para`, `create-note`, `journal`, `weekly-planner`, `weekly-review`, `monthly-planner`, `monthly-review`, `update-memory`, `this-week-status` |

## Install

Add the marketplace once, then install whichever plugins you want:

```bash
/plugin marketplace add thongntit/prompts
/plugin install coding-agent@thongntit-prompts
/plugin install obsidian-second-brain@thongntit-prompts
```

To update later:

```bash
/plugin marketplace update thongntit-prompts
```

## Repository structure

```
.claude-plugin/marketplace.json     # marketplace catalog
coding-agent/
  ├── .claude-plugin/plugin.json
  ├── skills/coding-agent/SKILL.md  # global ruleset (loads contextually)
  └── commands/                     # slash commands
obsidian-second-brain/
  ├── .claude-plugin/plugin.json
  └── skills/                       # 9 PARA / planning / review skills (auto-invoked)
```

## Contributing

To add a new plugin:

1. Create a top-level directory `<plugin-name>/`
2. Add `<plugin-name>/.claude-plugin/plugin.json` with `name`, `description`, `version`
3. Add components (`commands/`, `skills/`, `agents/`, `hooks/`, etc.)
4. Register it in `.claude-plugin/marketplace.json` under `plugins`
5. Validate with `claude plugin validate .`
