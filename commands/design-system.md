---
description: Design or audit a component design system
argument-hint: [init | audit | add-component <name>]
allowed-tools: [Read, Glob, Grep, Bash, Task]
---

# Design System

Design, initialize, or audit a component design system.

## Arguments

Action: $ARGUMENTS

## Workflow

### If action is `init` (or no existing system detected):

1. **Scaffold design tokens**
   - Colors: primary, secondary, neutral (8-10 shades), semantic (success, warning, error, info)
   - Spacing: 4px base unit scale (4, 8, 12, 16, 24, 32, 48, 64)
   - Typography: font families, modular scale (1.25 ratio), line heights
   - Shadows: elevation levels (sm, md, lg, xl)
   - Borders: radii, widths
   - Breakpoints: sm (640px), md (768px), lg (1024px), xl (1280px)

2. **Define component API conventions**
   - Standard props: `size`, `variant`, `disabled`, `className`
   - Composition pattern: composable children over complex prop objects
   - Ref forwarding pattern
   - Polymorphic `as` prop pattern

3. **Generate starter components**
   - Button (primary, secondary, outline, ghost, destructive)
   - Input (text, email, password, with label and error state)
   - Card (header, body, footer composition)

### If action is `audit`:

1. **Scan the codebase** for existing components, tokens, and patterns
2. **Identify inconsistencies**: duplicate colors, inconsistent spacing, mixed naming conventions
3. **Report**: what exists, what's missing, what needs consolidation

### If action is `add-component <name>`:

1. **Generate the component** following existing design system patterns
2. Include: component file, types, accessible markup, keyboard handling
3. Follow existing naming and prop conventions detected in the codebase
