---
name: create-note
description: ALWAYS use this skill when the user says "create note", "make note", "add note", "new note", "write a note", or creating ANY new .md file in an Obsidian vault. Validates PARA placement, enforces frontmatter conventions (created date, review tag), and matches existing note patterns before writing.
allowed-tools: Glob, Read, Write, Edit
---

# Create Note

Comprehensive guide for creating properly formatted notes in an Obsidian vault. Ensures consistency by checking templates and existing notes before creation.

## STEP 0 — PARA Validation (MANDATORY, do this first)

**Before creating any note, validate folder placement using the `para` skill.**

Apply the PARA decision framework:
1. Does it have a specific end goal and finish line? → `01_Project/`
2. Is it an ongoing responsibility with no end date? → `02_Area/`
3. Is it reference material to look up later? → `03_Resource/`
4. Is it inactive or completed? → `04_Archive/`

**If the user suggests a folder that violates PARA, push back and explain why before proceeding.**

Common mistakes to catch:
- User wants a project (has finish line) inside `02_Area/` → redirect to `01_Project/`
- User wants reference material (tool docs, analyses) inside `02_Area/` → redirect to `03_Resource/`
- User wants a learning tracker with tasks inside `03_Resource/` → check if it's actually an active project

Only proceed to creation after the folder is confirmed correct.

## ⚠️ MANDATORY Frontmatter Fields

Every newly created note MUST include `created` with today's date and a `review` tag:

```yaml
---
created: YYYY-MM-DD
tags:
  - review
  - [other relevant tags...]
---
```

These are non-negotiable for all new notes.

## Pre-Creation Checklist

Before creating any new note:

1. **Check the templates folder**
   - Look in `99_metadata/templates/` (or wherever the user keeps templates) for a relevant template
   - Common templates: Person, Place, Project, Book, Daily/Weekly note

2. **Check similar existing notes**
   - Search for notes of the same type/category and match their format
   - Example: creating a person note? Check existing entries in `03_Resource/Contact/` for format patterns

3. **Determine correct location** (PARA + topic)
   - Projects: `01_Project/`
   - Areas: `02_Area/`
   - Resources: `03_Resource/<topic>/`
   - Archives: `04_Archive/`

## Naming Conventions

### File names

- No special characters (avoid: `/ \ : * ? " < > |`)
- Use spaces (not hyphens or underscores)
- First header in the file must match the filename in Title Case
- Header MUST come **after** the frontmatter block

**Technical-folder convention (opinionated, optional):**
Some users enforce all-lowercase filenames inside technical folders (`03_Resource/Development/`, `03_Resource/AI/`, `03_Resource/English/`) so links resolve case-insensitively across systems. Follow whichever convention exists in the user's vault — check 2-3 sibling notes before naming.

### Folder names

- Lowercase with hyphens (kebab-case): `design-patterns/`, `react.js/`
- ❌ Avoid: spaces, uppercase, underscores in folder names

## Content Structure

```markdown
---
created: YYYY-MM-DD
tags:
  - review
---

# [Title Case of Filename]

[Content]
```

**❌ Wrong (header before frontmatter):**
```markdown
# My Note

---
created: YYYY-MM-DD
---
```

## Auto-Linking Entities

When creating notes, automatically link to:
- Existing notes whose filename matches an entity in the new note
- Related concepts (resources, projects, areas)

Strategy:
- Exact filename match (case-insensitive) → auto-link with `[[Note Name]]`
- Partial match → consider linking if relevant
- Generic terms (bug, fix, today, etc.) → skip

## Common Mistakes to Avoid

❌ Don't:
- Create notes without checking templates first
- Ignore existing note patterns in the same category
- Use hyphens or underscores in file names (use spaces)
- Use special characters in file names
- Forget the first header matching the filename
- Place notes in wrong PARA folders

✅ Do:
- Always include `created: YYYY-MM-DD` in every new note's frontmatter
- Always include `review` tag in every new note
- Always check templates folder first
- Look at 2-3 similar existing notes for format reference
- Match first header to filename (Title Case)
- Place in correct PARA folder structure
- Auto-link relevant entities
