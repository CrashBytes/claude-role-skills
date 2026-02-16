---
description: Run STRIDE threat analysis on a system or feature
argument-hint: <system, feature, or file path to analyze>
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Threat Model

Run a STRIDE threat analysis on a system, feature, or code path.

## Arguments

Target to analyze: $ARGUMENTS

## Workflow

1. **Define the scope**
   - If a file path is provided, read it and trace its data flows
   - If a system/feature name is provided, search the codebase for related files
   - Identify: entry points, data stores, external services, trust boundaries

2. **Map the data flow**
   - Identify all data inputs and outputs
   - Trace authentication and authorization paths
   - Map external service integrations
   - Identify trust boundary crossings

3. **Apply STRIDE to each component**

   For each component in the data flow, analyze:
   - **S**poofing: Can an attacker impersonate a user or service?
   - **T**ampering: Can data be modified in transit or at rest?
   - **R**epudiation: Can actions be performed without audit trails?
   - **I**nformation Disclosure: Can sensitive data leak?
   - **D**enial of Service: Can the service be made unavailable?
   - **E**levation of Privilege: Can an attacker gain unauthorized access?

4. **Score with DREAD**
   For each identified threat:
   - **D**amage potential (1-10)
   - **R**eproducibility (1-10)
   - **E**xploitability (1-10)
   - **A**ffected users (1-10)
   - **D**iscoverability (1-10)
   - Overall = average of all five

5. **Generate remediation plan**
   - Prioritize by DREAD score (Critical >7, High 5-7, Medium 3-5, Low <3)
   - Map each threat to OWASP Top 10 category where applicable
   - Provide specific code-level fix recommendations
   - Identify quick wins vs architectural changes

6. **Output**
   - Threat matrix table (Component × STRIDE categories)
   - Top threats ranked by DREAD score
   - Remediation plan with priority and effort estimates
   - Residual risk summary
