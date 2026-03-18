---
name: github-copilot-cli
description: "Use GitHub Copilot CLI via gh command. Explains code, suggests implementations, answers programming questions. Requires gh CLI and Copilot subscription."
---

# GitHub Copilot CLI Skill

Use this skill to invoke GitHub Copilot from OpenClaw.

## Requirements

- GitHub CLI (`gh`) installed
- Logged in to GitHub: `gh auth login`
- GitHub Copilot subscription (active)

## Commands

### Explain code
```bash
gh copilot explain "{code}"
```

### Suggest implementation
```bash
gh copilot suggest "{description}"
```

### General question
```bash
gh copilot -p "{question}"
```

## Examples

Explain Python code:
```bash
gh copilot explain "def fib(n): return n if n < 2 else fib(n-1) + fib(n-2)"
```

Suggest code:
```bash
gh copilot suggest "Write a function to reverse a string in Python"
```

Ask question:
```bash
gh copilot -p "What's the difference between list and tuple in Python?"
```

## Notes

- Copilot CLI may need to be downloaded on first run
- Responses are streamed and may take a few seconds
- Use quotes around multi-word arguments
