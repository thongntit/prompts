---
name: monthly-review
description: Aggregate raw monthly data and ask sharp questions. The user writes the review. AI does NOT analyze patterns, generate insights, or auto-edit long-term context files.
allowed-tools: Glob, Read, Grep, Write, Skill
---

# Monthly Review — User-Driven

Your job: **aggregate weekly data, show it raw, ask questions, format the user's answers.**
NOT your job: analyze project/area alignment, generate insights, recommend project changes, edit `about-me.md`.

---

## Step 1: Determine the month

Identify the month being reviewed (current or just-completed).

## Step 2: Aggregate raw data (mechanical only)

Pull these. No interpretation.

1. **Weekly grades** — from each weekly review section in `Periodic_notes/YYYY/weekly/YYYY-W##.md` (4–5 weeks)
2. **Monthly habit rates** — read habit completion from daily-note frontmatter for the month, sum/average per habit
3. **Tasks** — from the monthly note: count `[x]` vs `[ ]` for "Must Complete" and "Should Progress"
4. **Project status changes** — read `01_Project/*.md` frontmatter, list any project where `project-status` changed this month
5. **Headlines from each week** — pull the user's verbatim "headline" or top section from each weekly review

## Step 3: Show the data table to the user

```
## [Month YYYY] — Raw Data

Weekly grades:
| Week | Grade | User's headline (verbatim) |
| W##  | A-    | "shipped feature X"         |
| W##  | B     | "low capacity, family week" |
| W##  | ?     | [no review done]            |
| W##  | B+    | "catch-up week"             |

Habits (month average):
- [Habit]: X/N days (X%)
- [Habit]: X/N days (X%)

Monthly tasks:
- Must Complete: X/Y done
- Should Progress: X/Y done

Project status changes this month:
- Project A: Doing → Done
- Project B: Planned → Doing
- (none) for Project C

Daily journaling: X/N days had entries
```

**No commentary. No "trends". No emojis beyond what's in source data.**

## Step 4: Ask 4–6 sharp questions, ONE AT A TIME

Generate questions from the data. Wait for each answer.

### Default question set (adapt based on data)

1. **Headline question** — "Looking at the data, what's the headline of this month in one sentence?"
2. **Real progress** — "Which project or area got real progress this month? (Not 'I worked on it' — actual deliverable shipped.)"
3. **Stalled callout** — "Project X had no status change this month and was on the plan. What actually happened?" (use real project name from data)
4. **Pattern question** — "Habit Y was Z% — same as last month. Same blocker or different?"
5. **Decision** — "Continue, pause, or drop Project X? Pick one."
6. **Carry-forward** — "One thing to start next month, one thing to stop?"

### Question rules

Same as `weekly-review`:
- ✅ Use real data in the question (specific project names, specific numbers)
- ✅ Force decisions, not exploration
- ❌ No therapy-speak, no leading questions, no sympathy
- ❌ Don't fish for answers AI already has in mind

## Step 5: Accept answers verbatim

User answers via voice or short text. Their words go directly into the review. Do NOT rephrase.

Light formatting only: capitalize, fix typos, add bullets. Nothing else.

## Step 6: Output format

Append to the monthly note under `## Monthly Review`:

```markdown
## Monthly Review — [Month YYYY]

### Headline
[User's answer to Q1, verbatim]

### Data
- Weekly grades: [grades]
- Habits (month avg): [rates]
- Tasks: X/Y must, X/Y should
- Projects changed: [list]

### Real progress
[User's answer to Q2, verbatim]

### Stalled
[User's answer to Q3, verbatim]

### Pattern
[User's answer to Q4, verbatim]

### Decisions
- [User's project decisions from Q5]

### Start / Stop next month
- Start: [user's answer]
- Stop: [user's answer]
```

**Section headers reflect what the user said, not pre-canned templates.**

## Step 7: long-term-context update — explicit gate only

**NEVER auto-edit `99_metadata/about-me.md`** (or whatever long-term self-profile the user maintains).

After the review is written, ask ONCE:

> "Did anything this month change a long-term pattern in `about-me.md`? (Y/N)"

- **N** → done. No edit.
- **Y** → ask: "What changed? In which section?"
  - User describes the change in their own words
  - You draft a diff (small, surgical — touch only the section the user named)
  - Show the diff
  - Ask: "Apply? (Y/N)"
  - Apply only on explicit Y
  - Update `last-updated` in frontmatter

**Never propose pattern changes the user didn't name.** `about-me.md` is the user's self-profile, not yours.

---

## What this skill does NOT do

- ❌ Generate "What Went Well / What Went Poorly"
- ❌ Generate "Actionable Insights" or recommendations
- ❌ Analyze project/area alignment for the user
- ❌ Suggest projects to drop, pause, or pivot
- ❌ Identify patterns the user didn't name
- ❌ Auto-edit `about-me.md`
- ❌ Grade the month
- ❌ Compare to previous months unless user asks
- ❌ Soften or "improve" the user's wording

## Reminder for the AI running this skill

A monthly review's value is the user *processing* the month, not reading a summary of it. If you analyze for them, you steal the value. Aggregate data → ask sharp questions → format their answers. That's the entire job.
