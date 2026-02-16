---
description: Assess and plan a technology migration
argument-hint: <source-tech> to <target-tech> OR <system to assess>
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Migration Assessment

Assess a system for migration readiness and generate a migration plan.

## Arguments

Migration scope: $ARGUMENTS

## Workflow

1. **Assess current state**
   - If a codebase is available, scan for: languages, frameworks, dependencies, database types
   - Identify: code complexity, test coverage, documentation quality
   - Map external integrations and data flows
   - Estimate technical debt level

2. **Classify with the 7 Rs**
   For each component, recommend one of:
   - **Retain**: Keep as-is (low risk, low value to migrate)
   - **Retire**: Decommission (no longer needed)
   - **Rehost**: Lift-and-shift (move without changes)
   - **Replatform**: Lift-and-reshape (minor optimizations)
   - **Repurchase**: Replace with SaaS/COTS
   - **Refactor**: Re-architect for the target platform
   - **Reimagine**: Build from scratch

3. **Identify risks**
   - Data migration complexity (schema differences, data volume, transformation needs)
   - Integration points that will break
   - Feature parity gaps
   - Team skill gaps
   - Downtime requirements and business constraints

4. **Design migration strategy**
   - Recommend: Big Bang vs Strangler Fig vs Parallel Run
   - Phase breakdown with dependencies
   - Data migration approach (ETL, CDC, dual-write)
   - Rollback plan for each phase
   - Testing strategy (shadow traffic, parallel validation)

5. **Output**
   - Current state assessment
   - Component classification (7 Rs)
   - Risk register with mitigation strategies
   - Phased migration plan with timeline
   - Go/no-go checklist for each phase
   - Resource and skill requirements
