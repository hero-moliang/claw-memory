---
name: find-skills
description: "Discover and install skills from the open agent skills ecosystem using the Skills CLI (npx skills)."
---

# Find Skills

Discover and install skills from the open agent skills ecosystem.

## When to Use

- "how do I do X" where X might have an existing skill
- "find a skill for X"
- "is there a skill for X"
- "can you do X" where X is specialized
- Want to search for tools, templates, workflows
- Help with specific domains (design, testing, deployment, etc.)

## Skills CLI

The Skills CLI (`npx skills`) is the package manager for agent skills.

### Commands

```bash
# Search for skills
npx skills find [query]

# Install a skill
npx skills add <owner/repo@skill>

# Check for updates
npx skills check

# Update all skills
npx skills update
```

Browse: https://skills.sh/

## How to Find Skills

### Step 1: Understand the Need

Identify:
- Domain (React, testing, design, deployment)
- Specific task
- Whether a skill likely exists

### Step 2: Search

```bash
npx skills find react performance
npx skills find pr review
npx skills find changelog
```

### Step 3: Install

```bash
# Global install
npx skills add <owner/repo@skill> -g -y
```

## Common Categories

| Category | Example Queries |
|----------|-----------------|
| Web Dev | react, nextjs, typescript, css, tailwind |
| Testing | testing, jest, playwright, e2e |
| DevOps | deploy, docker, kubernetes, ci-cd |
| Documentation | docs, readme, changelog, api-docs |
| Code Quality | review, lint, refactor, best-practices |
| Design | ui, ux, design-system, accessibility |
| Productivity | workflow, automation, git |

## Tips

- Use specific keywords: "react testing" > "testing"
- Try alternatives: "deploy", "deployment", "ci-cd"
- Popular sources: `vercel-labs/agent-skills`, `ComposioHQ/awesome-claude-skills`

## When Not Found

If no skill exists:
1. Help directly with general capabilities
2. Suggest creating a skill: `npx skills init my-skill`
