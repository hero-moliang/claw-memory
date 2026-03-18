---
name: self-improving-agent
description: "Log learnings and errors to markdown files for continuous improvement. Coding agents can later process these into fixes, and important learnings get promoted to project memory."
---

# Self-Improvement Skill

Log learnings and errors to markdown files for continuous improvement.

## Quick Reference

| Situation | Action |
|-----------|--------|
| Command/operation fails | Log to `.learnings/ERRORS.md` |
| User corrects you | Log to `.learnings/LEARNINGS.md` with category `correction` |
| User wants missing feature | Log to `.learnings/FEATURE_REQUESTS.md` |
| API/external tool fails | Log to `.learnings/ERRORS.md` with integration details |
| Knowledge was outdated | Log to `.learnings/LEARNINGS.md` with category `knowledge_gap` |
| Found better approach | Log to `.learnings/LEARNINGS.md` with category `best_practice` |

## Setup

Create learning files:

```bash
mkdir -p .learnings
```

Create the log files:
- `LEARNINGS.md` — corrections, knowledge gaps, best practices
- `ERRORS.md` — command failures, exceptions
- `FEATURE_REQUESTS.md` — user-requested capabilities

## Logging Format

### Learning Entry

Append to `.learnings/LEARNINGS.md`:

```markdown
## [LRN-YYYYMMDD-XXX] category

**Logged**: ISO-8601 timestamp
**Priority**: low | medium | high | critical
**Status**: pending
**Area**: frontend | backend | infra | tests | docs | config

### Summary
One-line description of what was learned

### Details
Full context: what happened, what was wrong, what's correct

### Suggested Action
Specific fix or improvement to make

### Metadata
- Source: conversation | error | user_feedback
- Related Files: path/to/file.ext
- Tags: tag1, tag2
```

### Error Entry

Append to `.learnings/ERRORS.md`:

```markdown
## [ERR-YYYYMMDD-XXX] skill_or_command_name

**Logged**: ISO-8601 timestamp
**Priority**: high
**Status**: pending
**Area**: frontend | backend | infra | tests | docs | config

### Summary
Brief description of what failed

### Error
Actual error message or output

### Context
- Command/operation attempted
- Input or parameters used
- Environment details if relevant

### Suggested Fix
If identifiable, what might resolve this

### Metadata
- Reproducible: yes | no | unknown
- Related Files: path/to/file.ext
```

## ID Generation

Format: `TYPE-YYYYMMDD-XXX`
- TYPE: LRN (learning), ERR (error), FEAT (feature)
- YYYYMMDD: Current date
- XXX: Sequential number or random 3 chars

Examples: `LRN-20250115-001`, `ERR-20250115-A3F`

## Promoting to Project Memory

When a learning is broadly applicable, promote to:
- `CLAUDE.md` — Project facts, conventions
- `AGENTS.md` — Workflows and automation
- `SOUL.md` — Behavioral guidelines (OpenClaw)
- `TOOLS.md` — Tool capabilities (OpenClaw)

Update original entry: **Status**: pending → **Status**: promoted
