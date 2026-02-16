---
description: Run async daily standup and surface blockers
argument-hint: [team-member or blocker-focus]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Daily Standup

Run an async standup check-in and surface blockers.

## Arguments

Context provided: $ARGUMENTS

## Workflow

1. **Gather current state**
   - If a project management MCP server is connected, fetch in-progress items, recently completed items, and blocked items
   - If git is available, check recent commits for context: !`git log --oneline -5 2>/dev/null || echo "No git context"`

2. **Generate standup report for each team member** (or for the user)
   - **Yesterday:** What was completed or progressed
   - **Today:** What's planned
   - **Blockers:** Anything preventing progress

3. **Blocker analysis**
   - Identify items that have been in-progress for more than 2 days
   - Flag items with no recent activity
   - Suggest escalation paths for blockers (who to contact, what to try)

4. **Sprint health check**
   - Days remaining in sprint
   - Points completed vs committed
   - Burndown trajectory: on track / at risk / behind

5. **Output**
   - Standup summary per person
   - Blocker list with suggested actions
   - Sprint progress snapshot
