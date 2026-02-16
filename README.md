# Claude Role Skills

A Claude Code plugin with 7 role-based professional skills and 14 slash commands for software teams. Each skill teaches Claude how to act as a specific team role with deep domain knowledge, structured workflows, and MCP integration support.

## Skills

| Skill | Focus Areas |
|---|---|
| **scrum-master** | Sprint ceremonies, velocity tracking, impediment resolution, retrospective facilitation, burndown analysis |
| **product-owner** | User stories (INVEST), acceptance criteria, backlog management, prioritization (MoSCoW, RICE, WSJF), release planning |
| **product-manager** | Product strategy, roadmapping, market analysis (TAM/SAM/SOM), OKRs (AARRR), positioning, GTM |
| **ux-ui-developer** | Design systems, WCAG 2.1 AA accessibility, Nielsen's heuristics, responsive design, component architecture |
| **infosec-engineer** | Threat modeling (STRIDE/DREAD), OWASP Top 10, secure code review, incident response, compliance frameworks |
| **devops-engineer** | CI/CD (GitHub Actions, GitLab CI), Terraform, Docker/K8s, deployment strategies, monitoring (USE/RED), SLO/SLI |
| **software-migration-engineer** | Legacy assessment, 7 Rs of cloud migration, strangler fig, database migration, monolith decomposition |

## Commands

| Command | Role | Description |
|---|---|---|
| `/sprint-plan` | Scrum Master | Plan a sprint with capacity, goals, and story selection |
| `/retro` | Scrum Master | Facilitate a sprint retrospective (5 formats) |
| `/standup` | Scrum Master | Run async daily standup and surface blockers |
| `/user-story` | Product Owner | Write user stories with acceptance criteria |
| `/backlog-prioritize` | Product Owner | Prioritize backlog using RICE, MoSCoW, or WSJF |
| `/prd` | Product Manager | Draft a product requirements document |
| `/roadmap` | Product Manager | Build a product roadmap with themes and milestones |
| `/accessibility-audit` | UX/UI Developer | Run a WCAG 2.1 AA accessibility audit |
| `/design-system` | UX/UI Developer | Design, initialize, or audit a component design system |
| `/threat-model` | InfoSec Engineer | Run STRIDE threat analysis with DREAD scoring |
| `/security-review` | InfoSec Engineer | Security review of code changes |
| `/pipeline` | DevOps Engineer | Generate a CI/CD pipeline (GitHub Actions or GitLab CI) |
| `/deploy-strategy` | DevOps Engineer | Plan a deployment strategy (blue-green, canary, rolling) |
| `/migrate` | Migration Engineer | Assess and plan a technology migration |
| `/legacy-audit` | Migration Engineer | Audit a legacy system for modernization readiness |

## Installation

```bash
/plugin install role-based-skills@claude-plugin-directory
```

Or install directly from this repository:

```bash
/plugin install-from https://github.com/CrashBytes/claude-role-skills
```

## Usage

Skills activate automatically based on your prompts:

- "Help me plan our next sprint" → **scrum-master**
- "Write user stories for the checkout flow" → **product-owner**
- "Build a product roadmap for Q3" → **product-manager**
- "Review this component for accessibility" → **ux-ui-developer**
- "Threat model our authentication system" → **infosec-engineer**
- "Set up a CI/CD pipeline with GitHub Actions" → **devops-engineer**
- "Plan our migration from monolith to microservices" → **software-migration-engineer**

Commands can be invoked directly:

```
/sprint-plan 5-person team, 2-week sprint
/retro sailboat
/user-story checkout flow with guest checkout support
/threat-model src/auth/
/pipeline github node
/migrate Express.js to Next.js
```

## MCP Integrations

Every skill supports connecting to project management and DevOps tools via MCP servers. When connected, Claude can read real sprint data, create issues, update boards, and more.

| Platform | MCP Server | Auth |
|---|---|---|
| Jira / Confluence | [atlassian/atlassian-mcp-server](https://github.com/atlassian/atlassian-mcp-server) | OAuth |
| Azure DevOps | [microsoft/azure-devops-mcp](https://github.com/microsoft/azure-devops-mcp) | PAT |
| GitHub | [github/github-mcp-server](https://github.com/github/github-mcp-server) | PAT |
| GitLab | [@modelcontextprotocol/server-gitlab](https://www.npmjs.com/package/@modelcontextprotocol/server-gitlab) | PAT |
| Linear | [@ibraheem4/linear-mcp](https://www.npmjs.com/package/@ibraheem4/linear-mcp) | API key |
| Trello | [@delorenj/mcp-server-trello](https://www.npmjs.com/package/@delorenj/mcp-server-trello) | API key |
| Pusher Channels | [Pusher MCP](https://registry.modelcontextprotocol.io/?q=pusher&all=1) | App credentials |

See each skill's `references/integrations.md` for setup commands and role-specific actions.

## Structure

```
claude-role-skills/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── commands/
│   ├── sprint-plan.md           # Scrum Master
│   ├── retro.md
│   ├── standup.md
│   ├── user-story.md            # Product Owner
│   ├── backlog-prioritize.md
│   ├── prd.md                   # Product Manager
│   ├── roadmap.md
│   ├── accessibility-audit.md   # UX/UI Developer
│   ├── design-system.md
│   ├── threat-model.md          # InfoSec Engineer
│   ├── security-review.md
│   ├── pipeline.md              # DevOps Engineer
│   ├── deploy-strategy.md
│   ├── migrate.md               # Migration Engineer
│   └── legacy-audit.md
├── skills/
│   ├── scrum-master/
│   │   ├── SKILL.md
│   │   ├── LICENSE.txt
│   │   └── references/
│   ├── product-owner/
│   ├── product-manager/
│   ├── ux-ui-developer/
│   ├── infosec-engineer/
│   ├── devops-engineer/
│   └── software-migration-engineer/
├── LICENSE
└── README.md
```

## Tutorial

Learn how to build Claude Code skills from scratch:
[Building Claude Code Skills: A Scrum Master Skill for Anthropic's Official Repo](https://crashbytes.ai/tutorials/building-claude-code-skills-scrum-master-anthropic-2026)

## License

Apache 2.0 — see [LICENSE](LICENSE).
