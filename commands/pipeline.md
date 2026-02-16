---
description: Generate a CI/CD pipeline for GitHub Actions or GitLab CI
argument-hint: <platform: github | gitlab> [language/framework]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# CI/CD Pipeline Generator

Generate a production-ready CI/CD pipeline configuration.

## Arguments

Platform and stack: $ARGUMENTS

## Context

Project files: !`ls package.json requirements.txt Gemfile go.mod Cargo.toml pom.xml build.gradle composer.json 2>/dev/null || echo "No package files detected"`

## Workflow

1. **Detect platform and stack**
   - If platform is specified (github/gitlab), use it
   - If not, check for existing `.github/workflows/` or `.gitlab-ci.yml`
   - Auto-detect language from package files in the project root

2. **Design pipeline stages**
   - **Build**: Install dependencies, compile if needed
   - **Lint**: Code style and static analysis
   - **Test**: Unit tests with coverage reporting
   - **Security**: Dependency audit, SAST scan
   - **Deploy Staging**: Deploy to staging environment
   - **Deploy Production**: Deploy to production with approval gate

3. **Apply best practices**
   - Cache dependencies between runs
   - Run lint and test in parallel
   - Use matrix builds for multiple versions where applicable
   - Pin action/image versions (no `latest` tags)
   - Use environment secrets (never hardcode)
   - Add concurrency controls to prevent duplicate deployments
   - Set appropriate timeouts

4. **Configure deployment strategy**
   - Staging: auto-deploy on push to main
   - Production: manual approval or tag-based trigger
   - Include rollback instructions in comments

5. **Output**
   - Complete pipeline YAML file
   - Explanation of each stage
   - Required secrets and environment variables to configure
   - Instructions for first-time setup
