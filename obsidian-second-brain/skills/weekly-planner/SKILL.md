---
name: weekly-planner
description: Create a realistic, focused weekly plan (8–12 tasks max) by pulling from the active monthly plan, projects, and areas. Use when the user wants to plan their upcoming week.
allowed-tools: Glob, Read, Grep, Write
---

Generate a SHORT weekly plan. **8–12 tasks max.**

**Output to:** `Periodic_notes/YYYY/weekly/YYYY-W##.md` under `### Priority Tasks (this week)` (match the vault's weekly-note structure).

## Steps

1. Read `99_metadata/about-me.md` (if present) for context on focus areas and constraints
2. Read the current monthly note for "Must Complete" and "Should Progress" tasks
3. Read `02_Area/` for actionable todos
4. Read `01_Project/` for active projects
5. Check last week's unfinished tasks

## Priority Order

1. Monthly tasks (highest)
2. Active projects from `01_Project/`
3. Area todos from `02_Area/` (1–2 only)
4. Carry over unfinished from last week

## Scope Rules

- **8–12 tasks per week, hard cap**
- Assume 15–30 min/day capacity unless the user says otherwise
- Ask the user: "How many sessions for each project?" then break into Part 1, Part 2, ...

## Output Format

```markdown
### Priority Tasks (this week)

**Monthly: Must Complete**
- [ ] ~Task~ Task name (from [[Monthly]])
- [ ] ~Task~ Another task

**Projects**
- [ ] ~Task~ Project X Part 1 (deadline: YYYY-MM-DD)

**Areas**
- [ ] ~Task~ Task from [[Area note]]
- [ ] ~Task~ Read Inbox: 2 articles

---
**Scope:** N tasks | **Week:** W## YYYY-MM-DD to YYYY-MM-DD
```

## Rules

- Monthly > Projects > Areas (priority order)
- Don't count habits as tasks (habits live in daily notes)
- Use the `~Task~` global filter so tasks surface in dashboards/queries
- Keep it short — better to ship 8 than plan 15
