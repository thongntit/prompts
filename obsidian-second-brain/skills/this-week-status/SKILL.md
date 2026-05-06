---
name: this-week-status
description: Load current week overview — weekly note tasks plus all daily notes for the week. Use at session start or when the user asks about this week's status.
allowed-tools: Read, Bash, Glob
---

# This Week Status

Load a full picture of the current week. Read everything in parallel.

## Step 1: Determine dates

Run one bash command to get all needed values:

```bash
date +%V  # ISO week number
date +%Y  # year
date +%u  # day of week (1=Mon, 7=Sun)
```

The week runs Mon–Sun. Current week = W## from today's date.

## Step 2: Read everything in parallel

Issue ALL reads simultaneously:

1. **Weekly note** — `Periodic_notes/YYYY/weekly/YYYY-W##.md`
2. **Each daily note for the week** — `Periodic_notes/YYYY/<MonthName>/YYYY-MM-DD.md` for Mon through today (don't read future dates)

Use the current month folder. If the week spans two months (e.g., Apr 27 – May 3), read from both folders.

## Step 3: Build the status summary (internal context only)

Extract and hold in context:

- **Weekly tasks:** list all `- [ ]` and `- [x]` items from the weekly note
- **Daily notes:** for each day, capture the Work and Life sections verbatim. Mark `[empty]` if the section has no content.

## Step 4: Output

Reply with a compact status block:

```
## W## Status (Mon DD – Sun DD)

Tasks: X done / Y total
- [x] task name
- [ ] task name

Daily log:
- Mon DD: [Work: ... | Life: ...] or [empty]
- Tue DD: ...
...
```

Keep it scannable. No analysis, no opinions. Raw data only.
