---
description: Run a WCAG 2.1 AA accessibility audit on a component or page
argument-hint: <file-path or component-name>
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Accessibility Audit

Run a WCAG 2.1 AA compliance audit on a component, page, or set of files.

## Arguments

Target to audit: $ARGUMENTS

## Workflow

1. **Identify audit scope**
   - If a file path is provided, read it and any related component files
   - If a component name is provided, search the codebase for it
   - If no argument, scan for common UI entry points (pages, layouts, app root)

2. **Perceivable (WCAG 1.x)**
   - Color contrast: Check for hardcoded colors, verify 4.5:1 for normal text, 3:1 for large text
   - Images: Check all `<img>` tags have meaningful `alt` attributes (decorative images should use `alt=""`)
   - Text alternatives: Check for `aria-label` or `aria-labelledby` on icon-only buttons
   - Responsive: Check for viewport meta, no horizontal scroll at 320px

3. **Operable (WCAG 2.x)**
   - Keyboard: Check all interactive elements are natively focusable (`<button>`, `<a>`, `<input>`) or have `tabindex`
   - Focus indicators: Check for `outline: none` without replacement focus styles
   - Click targets: Check for minimum 44x44px touch targets
   - Skip navigation: Check for skip-to-content link

4. **Understandable (WCAG 3.x)**
   - Form labels: Check all inputs have associated `<label>` elements (not just placeholder)
   - Error messages: Check form validation provides specific, helpful messages
   - Language: Check `<html lang="...">` is set
   - Consistent navigation: Check for predictable layout patterns

5. **Robust (WCAG 4.x)**
   - Semantic HTML: Flag `<div>` or `<span>` used for interactive elements instead of `<button>`, `<a>`, `<nav>`
   - ARIA usage: Check ARIA attributes are used correctly (prefer native HTML over ARIA)
   - Duplicate IDs: Scan for duplicate `id` attributes
   - Valid nesting: Check heading hierarchy (no skipped levels)

6. **Output**
   - Issues grouped by WCAG principle
   - Severity rating: Critical / Major / Minor
   - Specific file, line number, and code snippet for each issue
   - Fix recommendation for each issue
   - Compliance summary: pass / partial / fail
