---
description: Draft a product requirements document
argument-hint: <product or feature name>
allowed-tools: [Read, Glob, Grep, Task]
---

# Product Requirements Document

Draft a structured PRD for a product or feature.

## Arguments

Product or feature: $ARGUMENTS

## Workflow

1. **Gather context**
   - Parse the product/feature description
   - If codebase is available, scan for existing implementation context
   - Identify the target market and user segments

2. **Draft PRD sections**

   **Executive Summary**
   - One paragraph: what, why, and for whom

   **Problem Statement**
   - What pain point does this solve?
   - How are users solving this today?
   - What's the cost of not solving it?

   **Goals and Success Metrics**
   - 2-3 measurable goals
   - Key metrics (AARRR: Acquisition, Activation, Retention, Revenue, Referral)
   - Target values and measurement timeline

   **User Personas**
   - Primary and secondary personas
   - Jobs to be done for each

   **Requirements**
   - Functional requirements (must-have, should-have, nice-to-have)
   - Non-functional requirements (performance, security, scalability, accessibility)
   - Out of scope (explicit exclusions)

   **User Flows**
   - Primary happy path
   - Key decision points
   - Error states and recovery

   **Technical Considerations**
   - Architecture implications
   - Integration points
   - Data requirements
   - Migration needs

   **Timeline and Milestones**
   - Phase breakdown with deliverables
   - Dependencies and risks

   **Open Questions**
   - Decisions that need stakeholder input
   - Areas requiring further research

3. **Output**
   - Complete PRD in markdown format
   - Ready for stakeholder review
