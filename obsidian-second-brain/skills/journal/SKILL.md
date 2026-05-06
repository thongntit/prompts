---
name: journal
description: Fast note-taking assistant for quick journaling with automatic entity linking. Optimized for speed and frictionless daily-note capture. Use when the user wants to add quick notes, tasks, or entries to their daily note.
allowed-tools: Read, Write, Edit, Glob, Grep
---

# Journal

Fast, frictionless note-taking for daily journaling. Optimized for speed with automatic entity linking and smart formatting.

## Quick Start

```
/journal [note content]
```

Examples:
```
/journal fixed upload bug in payment flow
/journal need to update React components for the new API
/journal learned about DNS configuration today
```

## Core Workflow

### 1. Parse Entry Type (Instant)

Identify entry type from context:
- **Task completion** → `[x]` (completed work)
- **New task** → `[ ]` (todo)
- **Problem/issue** → `📝`
- **Learning/insight** → `📝`
- **Idea** → `💭`
- **Food/calorie log** → `🍱` (also cross-post if a diet/fitness project exists — see §5)

### 2. Auto-Link Entities (Zero Confirmation)

**Priority search order:**
1. Projects: `01_Project/*.md`
2. Areas: `02_Area/**/*.md`
3. Resources: `03_Resource/**/*.md`

**Auto-link rules:**
- Exact filename match (case-insensitive) → auto-link immediately
- Partial filename match → auto-link
- No match → skip (don't ask, don't link)

**Never ask for confirmation.** Speed is the priority.

### 3. Format Entry

**Task completions:**
```markdown
[x] [Task description] - [[Auto-linked Entity]]
```

**New tasks:**
```markdown
[ ] [Task description] - [[Auto-linked Entity]]
```

**Problems/Notes:**
```markdown
📝 [Description] - [[Auto-linked Entity]]
```

**Ideas:**
```markdown
💭 [Idea] - [[Auto-linked Entity]]
```

### 4. Add to Daily Note

**Location:** `Periodic_notes/YYYY/<MonthName>/YYYY-MM-DD.md` (or wherever the vault keeps daily notes — match the vault's structure)

**Section placement:**
- Work-related → `### Work:` section
- Life/personal → `### Life:` section
- General notes → `### Notes:` section

Match the existing daily-note style. Preserve existing content. If no daily note exists, create one with a basic structure.

### 5. Special: Cross-Posting (Optional)

If the user maintains a topical tracking project (e.g. `01_Project/diet-project.md`, `01_Project/fitness-tracker.md`), cross-post relevant entries to it:

- Food/calorie logs → diet project's calorie log table
- Workout entries → fitness project
- Reading notes → reading project (if any)

Detect the relevant project by matching keywords in the entry against active project filenames. Skip if no matching project exists.

### 6. Optional: Create New Entity (Rare)

Only if an unlinked entity is:
- An important proper noun (a real person, a specific project name)
- Clearly note-worthy (not a generic term)

Then ask once:

```
"Create note for X?" Yes/No/Skip
```

Skip for: generic terms (bug, fix, DNS, authentication), common words, minor concepts already covered by existing notes.

## Examples

### Task with auto-link
```
User: "/journal fixed upload bug in payment flow"

Process:
1. Parse → Task completion [x]
2. Search → Found: "Payment Flow.md"
3. Auto-link → [[Payment Flow]]
4. Add → [x] Fixed upload bug in payment flow - [[Payment Flow]]
```

### Multiple auto-links
```
User: "/journal need to update React components for the new API"

Process:
1. Parse → New task [ ]
2. Search → Found: "React.md" and "API.md"
3. Add → [ ] Update React components for the new API - [[React]] [[API]]
```

### No matches (fast path)
```
User: "/journal learned about DNS configuration today"

Process:
1. Parse → Learning 📝
2. Search → no matches; "DNS" is generic → skip linking
3. Add → 📝 Learned about DNS configuration today
```

## Key Principles

✅ **Speed first** — auto-link immediately, no confirmation
✅ **Simple is better** — don't over-analyze entities
✅ **One question max** — only ask when creating an important new entity note
✅ **Skip generic terms** — don't link common words
✅ **Match existing daily-note style**
✅ **Frictionless** — the goal is fast, uninterrupted journaling

## Speed Targets

- Simple entry with auto-link: < 3 seconds
- Entry with new entity creation: < 10 seconds
- Entry with no links: < 2 seconds

The goal: make journaling so fast it becomes a frictionless habit.

## Related Skills

- `create-note` — for creating new entity notes (journal calls this when needed)
- `weekly-review` — uses journal entries for the weekly recap
- `monthly-review` — uses journal entries for monthly analysis
