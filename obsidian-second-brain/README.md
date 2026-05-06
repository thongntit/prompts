# Obsidian Second Brain

A Claude Code plugin for running an Obsidian vault as a [PARA](https://fortelabs.com/blog/para/)-based second brain: fast journaling, periodic planning and reviews, and memory-bank maintenance.

All components ship as **skills** — Claude auto-invokes them when the conversation context matches their description, so most of the time you just talk normally and the right skill fires.

## What you get

| Skill | What it does |
| :---- | :----------- |
| `para` | Strict PARA enforcer for "where should this note live?" decisions |
| `create-note` | Validates PARA placement, enforces frontmatter (`created`, `review` tag), matches existing patterns before writing |
| `journal` | Fast daily-note capture with auto-linking to existing entities (projects/areas/resources) |
| `weekly-planner` | Generates a focused 8–12 task weekly plan from the active monthly + projects + areas |
| `weekly-review` | Collects raw weekly data, asks sharp questions, formats answers verbatim — user writes the review, AI doesn't analyze |
| `monthly-planner` | Shows last month's data, asks the user to pick focus areas and projects (user-driven, not AI-generated) |
| `monthly-review` | Aggregates monthly data, asks 4–6 sharp questions, formats verbatim |
| `update-memory` | Refreshes the memory-bank files (`vaultStructure.md`, `noteConnections.md`) after significant vault changes |
| `this-week-status` | Loads weekly note + all daily notes for the current week — useful at session start |

## Install

```bash
/plugin marketplace add thongntit/prompts
/plugin install obsidian-second-brain@thongntit-prompts
```

## Vault conventions this plugin assumes

The skills assume a vault organized roughly like this. They work best when the structure matches; many will still work with adjustments if your folders differ.

```
01_Project/                          # PARA projects (have a finish line)
02_Area/                             # PARA areas (ongoing responsibilities)
03_Resource/                         # PARA resources (reference material)
04_Archive/                          # PARA archives (completed/inactive)
99_metadata/
  about-me.md                        # long-term self-profile (referenced by monthly-review)
  memory-bank/
    vaultStructure.md                # written by update-memory
    noteConnections.md               # written by update-memory
  templates/                         # note templates (checked by create-note)
Periodic_notes/
  YYYY/
    <MonthName>/YYYY-MM-DD.md        # daily notes (read by journal, this-week-status, reviews)
    weekly/YYYY-W##.md               # weekly notes (read/written by weekly-planner & weekly-review)
    YYYY-MM.md                       # monthly notes (read/written by monthly-planner & monthly-review)
```

### Frontmatter conventions

Skills look for these fields. None are strictly required, but they make the plugin work better:

- **Daily notes:** `meta-habits` (list of habit names completed that day) — used by weekly/monthly reviews to compute habit rates
- **Project notes:** `project-status` (`Doing` | `Planned` | `Todo` | `Done` | `Failed` | `Cancelled`), `AREA: "[[Area Name]]"`, `deadline: YYYY-MM-DD`
- **All new notes:** `created: YYYY-MM-DD`, `tags: [review, ...]` — enforced by `create-note`

## Design philosophy

The planning and review skills are deliberately **user-driven**, not AI-driven:

- Planners show data and ask which projects matter — they never pick for you
- Reviews aggregate raw numbers and ask sharp questions — they never grade or analyze
- Long-term files (`about-me.md`) are never auto-edited — explicit gate every time

The user pays the cost of writing the review = the user gets the value of reflection. If the AI writes the review for you, it steals the value.

## Related

- [PARA Method by Tiago Forte](https://fortelabs.com/blog/para/)
- [Obsidian Periodic Notes plugin](https://github.com/liamcain/obsidian-periodic-notes) — assumed for the daily/weekly/monthly note structure
