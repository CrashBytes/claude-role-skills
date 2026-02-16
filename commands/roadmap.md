---
description: Build a product roadmap with themes and milestones
argument-hint: <product name> [timeframe: quarterly | half-year | annual]
allowed-tools: [Read, Glob, Grep, Task]
---

# Product Roadmap

Build a structured product roadmap organized by themes and time horizons.

## Arguments

Product and timeframe: $ARGUMENTS

## Workflow

1. **Define time horizon**
   - If specified, use the requested timeframe
   - Default to quarterly (Now / Next / Later)
   - Options: quarterly, half-year, annual

2. **Identify strategic themes**
   - Group planned work into 3-5 strategic themes
   - Each theme should tie to a business objective
   - Examples: Growth, Retention, Platform Stability, Developer Experience

3. **Map initiatives to time horizons**

   **Now (current quarter):**
   - High confidence, well-defined scope
   - Active development or about to start
   - Specific deliverables and dates

   **Next (1-2 quarters out):**
   - Medium confidence, scope defined at epic level
   - Dependencies identified but not all resolved
   - Estimated quarter, not specific dates

   **Later (3+ quarters out):**
   - Lower confidence, directional
   - Themes and outcomes, not specific features
   - Subject to change based on learnings

4. **Add context to each initiative**
   - Business objective it serves
   - Target persona
   - Key metric it moves
   - Estimated effort (T-shirt size: S/M/L/XL)
   - Dependencies and risks

5. **Output**
   - Roadmap in table format (Theme × Time Horizon)
   - Key milestones and decision points
   - Resource implications
   - Assumptions and risks
