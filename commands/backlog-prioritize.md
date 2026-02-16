---
description: Prioritize backlog items using RICE, MoSCoW, or WSJF
argument-hint: [framework: rice | moscow | wsjf | value-effort]
allowed-tools: [Read, Glob, Grep, Task]
---

# Backlog Prioritization

Prioritize backlog items using a structured framework.

## Arguments

Framework or context: $ARGUMENTS

## Workflow

1. **Select framework**
   - If specified, use the requested framework
   - Default to **RICE** (most data-driven)
   - Available: RICE, MoSCoW, WSJF, Value vs Effort

2. **Gather backlog items**
   - If a project management MCP server is connected, fetch the current backlog
   - If not, ask the user to list their backlog items

3. **Apply the framework**

   **RICE:**
   - Reach: How many users affected per quarter?
   - Impact: Minimal (0.25), Low (0.5), Medium (1), High (2), Massive (3)
   - Confidence: Low (50%), Medium (80%), High (100%)
   - Effort: Person-months
   - Score = (Reach × Impact × Confidence) / Effort

   **MoSCoW:**
   - Must Have: Required for the release to be viable
   - Should Have: Important but not critical
   - Could Have: Nice to have
   - Won't Have: Explicitly out of scope for now

   **WSJF (Weighted Shortest Job First):**
   - Business Value + Time Criticality + Risk Reduction / Job Size
   - Use Fibonacci scale (1, 2, 3, 5, 8, 13) for each factor

   **Value vs Effort:**
   - Score value 1-10 and effort 1-10
   - Quadrants: Quick Wins (high value, low effort) → Major Projects → Fill-ins → Avoid

4. **Output**
   - Ranked list with scores
   - Visualization of the ranking (table format)
   - Top 5 recommendations with rationale
   - Items that need more information before they can be scored
