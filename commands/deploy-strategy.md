---
description: Plan a deployment strategy (blue-green, canary, rolling)
argument-hint: [strategy: blue-green | canary | rolling] [service-name]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Deployment Strategy

Plan and document a deployment strategy for a service.

## Arguments

Strategy and service: $ARGUMENTS

## Workflow

1. **Assess the service**
   - If a service name or path is provided, analyze the codebase
   - Identify: stateful vs stateless, database dependencies, external integrations
   - Check for existing deployment configs (Dockerfile, k8s manifests, terraform, docker-compose)

2. **Recommend strategy** (if not specified)
   - **Rolling**: Default for most stateless services. Zero-downtime, gradual replacement.
   - **Blue-Green**: When you need instant rollback. Two identical environments.
   - **Canary**: When you need to validate with real traffic. Gradual traffic shift.
   - Decision factors: risk tolerance, infrastructure cost, rollback speed, traffic patterns

3. **Design the strategy**

   **Rolling:**
   - Max unavailable / max surge settings
   - Health check configuration (readiness + liveness probes)
   - Graceful shutdown handling (drain connections before termination)

   **Blue-Green:**
   - Environment provisioning (identical blue and green)
   - Traffic switch mechanism (DNS, load balancer, router)
   - Database migration strategy (backward-compatible schemas)
   - Smoke test suite to run before switching

   **Canary:**
   - Traffic split percentages and timeline (1% → 5% → 25% → 100%)
   - Success criteria (error rate, latency percentiles, business metrics)
   - Automatic rollback triggers
   - Monitoring dashboard requirements

4. **Generate artifacts**
   - Deployment configuration files (k8s, terraform, or platform-specific)
   - Runbook: step-by-step deployment procedure
   - Rollback procedure
   - Monitoring checklist

5. **Output**
   - Strategy recommendation with rationale
   - Configuration files
   - Deployment runbook
   - Rollback plan
   - Monitoring and alerting requirements
