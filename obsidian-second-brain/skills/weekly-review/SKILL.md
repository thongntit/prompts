---
name: weekly-review
description: Run a weekly review by collecting raw data + asking sharp questions. The user writes the review through short voice/text answers; AI formats verbatim — no analysis, no grading, no insights generation.
allowed-tools: Glob, Read, Grep, Write, Skill
---

# Weekly Review — User-Driven

Your job: **collect data, ask questions, format answers verbatim.**
NOT your job: analyze patterns, grade the week, generate insights, soften feedback.

**Output to:** `Periodic_notes/YYYY/weekly/YYYY-W##.md` under `## Weekly Review`.

---

## Step 1: Determine the week

- Sunday → this week (W##)
- Mon–Sat → last week (W##−1)

## Step 2: Collect raw data (mechanical only)

Pull these. No interpretation.

1. **Habits** — if the user tracks habits in daily-note frontmatter (e.g. a `meta-habits` list), read each daily note for the week and tally completions per habit
2. **Tasks** — count `[x]` vs `[ ]` in the weekly note
3. **Daily-note quotes** — pull the user's own words verbatim from each daily note (Work + Life sections). Empty notes → mark `[empty]`
4. **Last 4 weeks' grades** — pull from previous weekly review sections (just numbers/letters)

## Step 3: Show the data table to the user

Format like this. **No commentary. No emojis except what's in the source.**

```
## Week ## — Raw Data

Daily notes (your words):
- Mon: [verbatim quote or "empty"]
- Tue: [verbatim quote or "empty"]
- Wed: [verbatim quote or "empty"]
- Thu: [verbatim quote or "empty"]
- Fri: [verbatim quote or "empty"]
- Sat: [verbatim quote or "empty"]
- Sun: [verbatim quote or "empty"]

Habits: [habit]: X/7 | [habit]: X/7 | ...
Tasks: X/Y completed
Last 4 grades: [X], [X], [X], [X]
```

## Step 4: Ask sharp questions, ONE AT A TIME

Generate 3–5 questions based on the data. Wait for each answer before asking the next.

### Question rules

✅ **Ask:**
- Clarifications when data is ambiguous ("Wed says 'tired'. Work-tired or family-tired?")
- Pattern callouts using actual data ("Habit X: 0/7 — third week in a row. What's the real blocker?")
- Challenges to weak answers using user's own data ("You said 'too busy' but Sat shows 4 hours of leisure. What was actually blocking it?")
- Decision-forcing options ("Drop X, restart X, or commit to a smaller pace? Pick one.")

❌ **Never ask:**
- "How did that make you feel?"
- "Do you think you might be overcommitted?"
- "What could you do differently?"
- Anything that fishes for an answer you already have in mind
- Sympathetic questions ("Sounds like a hard week — was it?")

### Question count

- Thin week (most days empty/light): 2–3 questions
- Normal week: 3–4 questions
- Heavy week with multiple patterns: 5 questions max

**Never more than 5.** This is a review, not therapy.

## Step 5: Accept answers verbatim

The user will likely answer via voice dictation or short text. Their words go directly into the review. Do NOT rephrase.

❌ User says: "skipped workout tired wed kid sick thu"
❌ AI writes: "Skipped workout due to fatigue on Wednesday and child's illness on Thursday"

✅ AI writes: "Skipped workout — tired Wed, kid sick Thu"

Light formatting only: capitalize sentence starts, fix obvious typos, add bullet markers. Nothing else.

## Step 6: Output format

```markdown
## Weekly Review

**Week:** YYYY-MM-DD to YYYY-MM-DD (W##)

### Data
- Habits: [tally]
- Tasks: X/Y
- Daily journaling: X/7 days

### [User-named headline / Q1 answer]
[Their words verbatim]

### [Q2 answer if relevant]
[Their words verbatim]

### Decisions made
- [From decision-forcing questions: e.g., "User chose B: smaller workout target"]

### Carry into next week
- [ ] [User's next-week item if they named one]
```

**Section headers should reflect what the user actually said, not pre-canned templates.**

## Step 7: Update monthly note

Mark this week's tasks as `[x]` if the user confirmed completion. Do NOT mark anything the user didn't explicitly confirm.

---

## What this skill does NOT do

- ❌ Generate "What Went Well / What Went Poorly" sections
- ❌ Grade the week (no A/B/C/D/F)
- ❌ Identify patterns for the user (only ask the user to identify them)
- ❌ Suggest what to do next week
- ❌ Soften or "improve" the user's wording
- ❌ Add encouragement, sympathy, or motivation
- ❌ Auto-edit `about-me.md` or any long-term-pattern file

## Reminder for the AI running this skill

The user pays the cost of writing the review = the user gets the value of reflection. If you write the review for them, you steal the value. Stay in your lane: data collector + question asker + scribe.
