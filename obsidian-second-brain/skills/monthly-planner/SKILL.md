---
name: monthly-planner
description: Show last month's data and ask the user to pick focus areas and projects. AI does NOT generate focus areas, set targets, or pick projects. User decides; AI formats.
allowed-tools: Glob, Read, Grep, Write, Skill
---

# Monthly Planner — User-Driven

Your job: **show last month's data, ask sharp questions, format the user's decisions.**
NOT your job: pick focus areas, choose projects, set targets, generate "Why/Target/When" content.

---

## Step 1: Identify the month being planned

Current month or upcoming month being planned.

## Step 2: Aggregate last month's data (mechanical only)

Pull these. No interpretation.

1. **Last month's review** — read the `## Monthly Review` section from the previous month's note (the user's own words from the user-driven `monthly-review` skill)
2. **Habit rates** — last month's monthly average per habit (read daily-note frontmatter if the user tracks habits there)
3. **Task completion** — last month: Must Complete X/Y, Should Progress X/Y
4. **Project status snapshot** — read all `01_Project/*.md` frontmatter, list:
   - Active (`Doing`)
   - Planned but not started (`Planned`, `Todo`)
   - Overdue (deadline < today, status not `Done`)
5. **Area touchpoints last month** — for each area in `02_Area/`, count projects with `AREA: "[[Area Name]]"` whose `project-status` changed last month
6. **Carry-over** — tasks from last month's monthly note still `[ ]` (not done)

## Step 3: Show the data table to the user

```
## [Month YYYY] Planning — Last Month Data

Last month's review (your words):
[paste the user's verbatim "Headline" from last monthly review]
[paste their "Pattern" answer]
[paste their "Start/Stop" decisions]

Last month performance:
- Must Complete: X/Y done
- Should Progress: X/Y done
- Habits avg: [habit]: X% | [habit]: X% | ...

Projects right now:
- Active (Doing): [list]
- Planned/Todo: [list]
- Overdue: [list with how many days overdue]

Area touchpoints last month:
- [Area name]: X projects active
- [Area name]: X projects active

Carry-over from last month (still open):
- [list of [ ] tasks]
```

**No commentary. No "trends". No suggestions.**

## Step 4: Ask 5–7 questions, ONE AT A TIME

Wait for each answer.

### Default question set

1. **Theme** — "One sentence: what is this month about?"
2. **Focus area #1** — "Pick your top focus area for the month. From your areas: [list]. Which one?"
3. **Focus area #2** — "Second focus area. Or 'none' if you only want one."
4. **Focus area #3** — "Third focus area, or 'none'. Reminder: fewer focus areas usually executes better."
5. **Must Complete projects** — "Pick at most 3 projects from this list to mark Must Complete: [show active + overdue]. Which?"
6. **Should Progress projects** — "Pick up to 3 more for Should Progress, or 'none'."
7. **Carry-over decision** — "These tasks didn't finish last month: [list]. For each: carry, drop, or move to next month?"

### Question rules

✅ **Ask:**
- Specific picks from concrete lists (you provide the list, user picks)
- Decisions, not exploration
- Challenges using user's own past patterns ("You picked 5 focus areas last month — completed 1. Still want 3 this month?")

❌ **Never:**
- Suggest a focus area
- Recommend a project
- Set a target number ("aim for 3x/week" — let the user set it)
- Soften the user's choices ("are you sure you want only one?" with disapproving tone)
- Therapy-speak

### Realism nudge (allowed, once)

If the user picks ≥4 focus areas OR ≥4 Must Complete projects, ask once:

> "Last month you completed X/Y. With 4+ focus areas you're planning ~3× last month's output. Sure?"

User says yes → accept it, move on. Don't ask again.

## Step 5: Optional target-setting (user-driven)

For each focus area picked, ask:

> "Target for [area]? (e.g., '15 min/day', '2 sessions/week', or 'no target')"

User answers in their own words. Do NOT suggest. If they say "no target", accept it.

## Step 6: Output format

Write to the monthly note. **Use the user's exact wording.**

```markdown
# [Month YYYY] Plan

## Theme
[User's Q1 answer, verbatim]

## Focus Areas
1. [User's Q2 answer] — Target: [user's target or "no target"]
2. [User's Q3 answer if not "none"] — Target: [...]
3. [User's Q4 answer if not "none"] — Target: [...]

## Monthly Tasks

### Must Complete
- [ ] [Project from Q5]
- [ ] [Project from Q5]
- [ ] [Project from Q5]

### Should Progress
- [ ] [Project from Q6]
- [ ] [Project from Q6]

### Carry-over from last month
- [ ] [tasks user said carry]
- ~~[tasks user said drop]~~ (dropped)
```

## Step 7: Save and exit

Write the file. Do NOT add a "Validation Questions" section. Do NOT ask "are these targets realistic" — that was the question you already asked in Step 4 if applicable.

---

## What this skill does NOT do

- ❌ Generate focus areas
- ❌ Recommend projects to mark Must Complete
- ❌ Set targets (user sets them or skips them)
- ❌ Write "Why" statements for focus areas
- ❌ Compare to last month with commentary ("you're improving!")
- ❌ Auto-pick carry-overs
- ❌ Add "Stretch Goals" or "Protected Time" sections the user didn't ask for
- ❌ Bold "critical" items the user didn't mark critical

## Reminder for the AI running this skill

A monthly plan's value is the user *deciding* what matters this month. If you decide for them, they execute someone else's plan — and execution rates collapse.

Show data → ask picks → format choices. That's the entire job.
