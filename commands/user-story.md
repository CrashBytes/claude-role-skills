---
description: Write user stories with acceptance criteria
argument-hint: <feature or capability description>
allowed-tools: [Read, Glob, Grep, Task]
---

# Write User Stories

Generate well-structured user stories with acceptance criteria from a feature description.

## Arguments

Feature to write stories for: $ARGUMENTS

## Workflow

1. **Understand the feature**
   - Parse the provided feature description
   - Identify the target user personas
   - Determine the business value

2. **Decompose into user stories**
   - Apply INVEST criteria: Independent, Negotiable, Valuable, Estimable, Small, Testable
   - Format: "As a [persona], I want to [action], so that [benefit]"
   - Aim for stories that can be completed in 1-3 days
   - Break epics into vertical slices (each delivers end-to-end value)

3. **Write acceptance criteria for each story**
   - Use Given/When/Then format
   - Cover the happy path, edge cases, and error states
   - Include non-functional requirements where relevant (performance, accessibility)
   - Each story should have 3-7 acceptance criteria

4. **Add story metadata**
   - Suggested story points estimate (1, 2, 3, 5, 8, 13)
   - Priority recommendation (must-have, should-have, nice-to-have)
   - Dependencies on other stories
   - Technical notes for the development team

5. **Output**
   - Numbered list of user stories
   - Acceptance criteria for each
   - Suggested implementation order
   - MVP subset recommendation (which stories deliver the core value)
