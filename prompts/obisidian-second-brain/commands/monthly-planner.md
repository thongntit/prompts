---
description: "Create a comprehensive monthly plan by analyzing the previous month's review, current projects, and area resolutions"
---

You are tasked with generating a comprehensive monthly plan that builds upon the previous month's review to create an actionable plan for the upcoming month. Follow these steps:

1. **Locate the Monthly Note Template:**
   - Read the template from `99_metadata/templates/Monthly note Template.md`
   - This template contains the structure you should follow

2. **Identify the current month and year:**
   - Determine which month needs planning

3. **Gather context from previous month:**
   - Read the previous month's note from `Periodic_notes/YYYY/Month/Month.md`
   - Extract key insights from the Reflect section:
     - What worked well vs. what didn't work
     - Completion rates (weekly planning, financial reviews, daily journaling)
     - Projects completed vs. started vs. not started
     - Areas that progressed vs. stagnated
     - Key lessons learned and insights
     - Engagement patterns (boom-bust cycles, consistency issues)
     - Success metrics achieved vs. missed

4. **Analyze current state:**
   - Query active projects from `01_Project` directory (filter by #Project tag, exclude archived)
   - Query area resolutions from `02_Area` directory (filter by #Area tag)
   - Identify which projects are:
     - Overdue and need immediate priority
     - In progress and should continue
     - Planned but not started
   - Identify which areas need focus based on previous month's results

5. **Generate the monthly plan with smart insights:**

   **Your primary focus is to make this month MORE EFFICIENT than the last by:**

   **A. Learning from Failures:**
   - If weekly planning completion was low (e.g., 20%), identify WHY and set realistic improvement target (e.g., 75%, not 100%)
   - If personal projects had 0% completion, create PROTECTED time blocks with same rigor as work meetings
   - If daily systems were too heavy/complex, SIMPLIFY them (e.g., 5-minute rule instead of 30-minute journaling)
   - If habits weren't tracked, reduce number to 2-3 key habits only
   - If "boom-bust" pattern occurred, focus on SUSTAINABLE middle ground, not intensity

   **B. Building on Successes:**
   - Identify what got completed and WHY (e.g., "Week 42 Effect" - planning led to 4 completions)
   - Make successful strategies NON-NEGOTIABLE (e.g., if planning drove results, make it mandatory)
   - Repeat time management approaches that worked
   - Continue project types that succeeded (e.g., work/learning projects vs. personal projects)

   **C. Setting Realistic Targets:**
   - Don't plan for 100% if previous was 20% - aim for 75%
   - Critical goals: 3-4 maximum (not 10)
   - Important goals: 3-4 maximum
   - Stretch goals: truly optional, not disguised requirements
   - Base targets on actual previous performance, not ideal wishes

   **D. Creating Concrete Commitments:**
   - Turn insights into SPECIFIC time blocks (e.g., "Sunday 8:00-8:15 PM: Weekly planning")
   - Turn failures into PROTECTED time (e.g., "Friday 7-10 PM: Personal projects - treat as work meeting")
   - Turn challenges into MITIGATION strategies (e.g., if personal projects fail, schedule them like work)
   - Add accountability mechanisms (e.g., track in weekly notes, review in weekly planning)

   **E. Balancing Priorities:**
   - Overdue projects need priority but NOT at expense of everything
   - Personal goals need SAME rigor as work goals (time blocks, accountability)
   - Work-life balance: protect personal time EXPLICITLY
   - Don't overcommit: one main focus per week is better than five half-done projects

   **F. Identifying Patterns to Break:**
   - If work projects always complete but personal never do → schedule personal like work
   - If planning only happened 1/5 weeks → make it a ritual with specific trigger (e.g., Sunday dinner → planning)
   - If engagement is "all or nothing" → focus on consistency over intensity
   - If habits get dropped → simplify to 2-3 key habits with 5-minute rule

6. **Fill out the template with:**
   - **Key Insights from Last Month:** 3-5 most critical lessons that will shape this month
   - **Area Resolution Focus:** Prioritize based on last month's results (primary = what succeeded, secondary = what needs attention)
   - **Projects to Prioritize:**
     - High Priority: Overdue projects + critical work projects (2-3 max)
     - Medium Priority: Important but not urgent (2-3 max)
     - Low Priority/On Hold: Explicitly defer to reduce cognitive load
   - **Monthly Strategy:**
     - Primary Goal: One main focus (the highest leverage activity from last month)
     - Secondary Goal: Second most important
     - Tertiary Goal: Supporting habit/system
   - **Time Blocks:** Concrete schedules based on what worked/failed last month
   - **Monthly Objectives:** Categorized by Critical/Important/Stretch with realistic counts
   - **Success Metrics:** Based on previous month's baseline (e.g., "75% vs. October's 20%")
   - **Challenges & Mitigation:** Address specific patterns from last month with concrete strategies
   - **Monthly Commitment:** 5 commitments that directly address last month's weaknesses and build on strengths

7. **Use the template structure but customize all content:**
   - Fill in specific area names and goals
   - Fill in actual project names and contexts
   - Fill in realistic time blocks based on user's schedule patterns
   - Fill in concrete metrics based on previous month's data
   - Fill in specific challenges observed from previous month

8. **After generating the plan, provide:**
   - A brief summary of the 3-5 key changes from last month (e.g., "Increased weekly planning target from 20% to 75%")
   - Highlight the ONE highest-leverage activity for the month
   - Ask validation questions:
     - "Does this plan feel realistic based on last month's patterns?"
     - "Are the time commitments achievable given your actual schedule?"
     - "Should I adjust any priorities or add/remove any focus areas?"

**Key Principle:** The plan should be ACTIONABLE and REALISTIC, not aspirational. Better to complete 75% of a realistic plan than 20% of an ambitious one.

Present the complete plan in markdown format ready to be copied into the monthly note.
