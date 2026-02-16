---
description: Audit a legacy system for modernization readiness
argument-hint: [file-path or directory to audit]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Legacy System Audit

Audit a codebase to assess modernization readiness and identify migration priorities.

## Arguments

Target to audit: $ARGUMENTS

## Workflow

1. **Inventory the system**
   - Scan the codebase structure and file types
   - Identify languages, frameworks, and their versions
   - Map dependency graph (direct and transitive)
   - Detect deprecated APIs and end-of-life dependencies

2. **Assess code health**
   - Estimate test coverage (presence and quality of test files)
   - Check for documentation (README, API docs, inline comments)
   - Identify code smells: god classes, long methods, circular dependencies
   - Check for hardcoded configuration, magic numbers, dead code

3. **Evaluate architecture**
   - Monolith vs modular vs microservices
   - Coupling analysis: how tightly are components connected?
   - Identify natural service boundaries (bounded contexts)
   - Database structure: single DB, shared schemas, data ownership

4. **Security assessment**
   - Outdated dependencies with known CVEs
   - Authentication and authorization patterns
   - Secret management practices
   - Input validation and output encoding

5. **Score modernization readiness**
   Rate each dimension 1-5:
   - Code quality and maintainability
   - Test coverage and confidence
   - Documentation completeness
   - Architecture modularity
   - Dependency health
   - Security posture
   - Team knowledge and skills

6. **Output**
   - System inventory summary
   - Health scorecard (radar chart dimensions)
   - Top 10 modernization priorities ranked by impact and effort
   - Recommended migration approach (based on scores)
   - Quick wins that can be done before a full migration
