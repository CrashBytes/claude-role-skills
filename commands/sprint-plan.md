---
description: Plan a sprint with capacity, goals, and story selection
argument-hint: [team-size or sprint-details]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Sprint Planning

Facilitate a sprint planning session for the team.

## Arguments

Sprint context provided: $ARGUMENTS

## Workflow

1. **Gather context**
   - If a project management MCP server is connected (Jira, Linear, Azure DevOps, GitHub, GitLab), fetch the current backlog and previous sprint velocity
   - If no MCP server, ask the user for: team size, sprint duration, average velocity, and backlog items

2. **Calculate capacity**
   - Formula: `Available days × Team members × Focus factor (0.7) = Capacity in person-days`
   - Account for holidays, PTO, and meetings
   - Convert to story points using the team's historical ratio

3. **Define sprint goal**
   - Propose a sprint goal that ties to a business outcome
   - Format: "By the end of this sprint, [stakeholder] will be able to [capability]"
   - The goal should be achievable within the calculated capacity

4. **Select stories**
   - Pull from the top of the prioritized backlog
   - Stop when total story points approach 85% of capacity (leave buffer)
   - Flag any stories missing acceptance criteria or estimates
   - Identify dependencies between selected stories

5. **Output sprint plan**
   - Sprint goal
   - Capacity calculation breakdown
   - Selected stories with estimates
   - Dependencies and risks
   - Stretch goals (next 2-3 stories if capacity allows)
