# Claude Role Skills

A Claude Code plugin with 7 role-based professional skills for software teams. Each skill teaches Claude how to act as a specific team role with deep domain knowledge, structured workflows, and MCP integration support.

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

## Installation

```bash
/plugin install role-based-skills@claude-plugin-directory
```

Or install directly from this repository:

```bash
/plugin install-from https://github.com/CrashBytes/claude-role-skills
```

## Usage

Skills activate automatically based on your prompts. Examples:

- "Help me plan our next sprint" → **scrum-master**
- "Write user stories for the checkout flow" → **product-owner**
- "Build a product roadmap for Q3" → **product-manager**
- "Review this component for accessibility" → **ux-ui-developer**
- "Threat model our authentication system" → **infosec-engineer**
- "Set up a CI/CD pipeline with GitHub Actions" → **devops-engineer**
- "Plan our migration from monolith to microservices" → **software-migration-engineer**

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
├── skills/
│   ├── scrum-master/
│   │   ├── SKILL.md             # Core instructions
│   │   ├── LICENSE.txt          # Apache 2.0
│   │   └── references/
│   │       ├── retrospective-formats.md
│   │       └── integrations.md
│   ├── product-owner/
│   ├── product-manager/
│   ├── ux-ui-developer/
│   ├── infosec-engineer/
│   ├── devops-engineer/
│   └── software-migration-engineer/
└── README.md
```

## Tutorial

Learn how to build Claude Code skills from scratch:
[Building Claude Code Skills: A Scrum Master Skill for Anthropic's Official Repo](https://crashbytes.com/tutorials/building-claude-code-skills-scrum-master-anthropic-2026)

## License

Apache 2.0 — see [LICENSE.txt](skills/scrum-master/LICENSE.txt) in each skill directory.
