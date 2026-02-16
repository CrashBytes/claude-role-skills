---
description: Security review of code changes or a file
argument-hint: <file-path or git-ref>
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Security Review

Perform a security-focused code review on a file or set of changes.

## Arguments

Target to review: $ARGUMENTS

## Context

Recent changes: !`git diff --stat HEAD~1 2>/dev/null || echo "No git context"`

## Workflow

1. **Identify review scope**
   - If a file path is provided, read it
   - If a git ref is provided, get the diff
   - If no argument, review staged or recent changes

2. **Check OWASP Top 10**
   - **Injection**: SQL, NoSQL, OS command, LDAP injection via unsanitized inputs
   - **Broken Auth**: Hardcoded credentials, weak session management, missing MFA hooks
   - **Sensitive Data**: Secrets in code, unencrypted PII, excessive logging of sensitive data
   - **XXE / Deserialization**: Unsafe XML parsing, insecure deserialization
   - **Broken Access Control**: Missing authorization checks, IDOR vulnerabilities, path traversal
   - **Misconfig**: Debug mode enabled, default credentials, verbose error messages in production
   - **XSS**: Unescaped user input in HTML output, innerHTML usage, dangerouslySetInnerHTML
   - **Insecure Dependencies**: Known CVEs in dependencies (check package.json/requirements.txt)
   - **Insufficient Logging**: Missing audit trails for auth events and data access
   - **SSRF**: Unvalidated URLs in server-side requests

3. **Check secure coding patterns**
   - Input validation at trust boundaries
   - Output encoding for the correct context (HTML, URL, JS, CSS)
   - Parameterized queries (no string concatenation in SQL)
   - Proper error handling (no stack traces to users)
   - Secure defaults (deny by default, least privilege)
   - Secrets management (env vars or vault, not hardcoded)

4. **Check dependency security**
   - If package.json exists: `npm audit` findings
   - If requirements.txt exists: known vulnerabilities
   - Flag any pinned versions with known CVEs

5. **Output**
   - Issues grouped by severity: Critical / High / Medium / Low / Info
   - Each issue: file, line, vulnerability type, code snippet, fix recommendation
   - Summary: total issues by severity, overall risk assessment
