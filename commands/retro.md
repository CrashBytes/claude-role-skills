---
description: Facilitate a sprint retrospective
argument-hint: [format: start-stop-continue | 4ls | sailboat | timeline | fishbone]
allowed-tools: [Read, Glob, Grep, Task]
---

# Sprint Retrospective

Facilitate a structured sprint retrospective.

## Arguments

Requested format: $ARGUMENTS

## Workflow

1. **Select format**
   - If a format is specified, use it
   - If not specified, default to **Start/Stop/Continue** (most universal)
   - Available formats: start-stop-continue, 4ls, sailboat, timeline, fishbone

2. **Set the stage** (2 min)
   - State the Prime Directive: "Regardless of what we discover, we understand and truly believe that everyone did the best job they could, given what they knew at the time, their skills and abilities, the resources available, and the situation at hand."
   - If a project management MCP server is connected, pull the sprint metrics (velocity, burndown, completed vs committed)

3. **Run the format**

   **Start/Stop/Continue:**
   - Ask: What should we START doing? What should we STOP doing? What should we CONTINUE doing?
   - Generate 3-5 prompting questions for each category based on common team patterns

   **4Ls (Liked, Learned, Lacked, Longed For):**
   - Ask for items in each L category
   - Group related items across categories

   **Sailboat:**
   - Wind (what propels us forward), Anchor (what holds us back), Rocks (risks ahead), Island (our goal)
   - Map items to actionable improvements

   **Timeline:**
   - Walk through the sprint week by week
   - Mark highs, lows, and key events
   - Identify patterns across the timeline

   **Fishbone / 5 Whys:**
   - Identify the main problem from the sprint
   - Apply 5 Whys to find root cause
   - Categorize causes: People, Process, Tools, Environment

4. **Generate action items**
   - Each action item must have: owner, due date, and success criteria
   - Limit to 3 action items (more won't get done)
   - Reference previous retro actions if available

5. **Output the retro summary**
   - Format chosen and why
   - Key themes identified
   - Top 3 action items with owners
   - Team health pulse (improving / stable / declining)
