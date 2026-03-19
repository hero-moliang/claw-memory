# Learnings Log

Log corrections, knowledge gaps, and best practices here.

## Format

```markdown
## [LRN-YYYYMMDD-XXX] category

**Logged**: ISO-8601 timestamp
**Priority**: low | medium | high | critical
**Status**: pending
**Area**: frontend | backend | infra | tests | docs | config

### Summary
One-line description

### Details
Full context

### Suggested Action
Specific fix

### Metadata
- Source: conversation | error | user_feedback
- Related Files: 
- Tags: 
```

---

## [LRN-20250318-001] best_practice

**Logged**: 2026-03-18T21:01:00+08:00
**Priority**: medium
**Status**: pending
**Area**: config

### Summary
在 macOS (ARM64) 上安装 GitHub CLI (gh) 和 Copilot 扩展的完整步骤

### Details
用户想要在 OpenClaw 中使用 github-copilot-cli skill，但系统未安装 gh CLI。通过以下步骤完成安装：

1. 从 GitHub releases 下载对应架构的预编译二进制文件
   - URL: https://github.com/cli/cli/releases/download/v2.88.1/gh_2.88.1_macOS_arm64.zip
   - 注意：macOS 版本是 .zip 格式，不是 .tar.gz

2. 解压并移动到本地 bin 目录
   ```bash
   unzip gh_2.88.1_macOS_arm64.zip
   mkdir -p ~/.local/bin
   mv gh_2.88.1_macOS_arm64/bin/gh ~/.local/bin/
   ```

3. 添加到 PATH（永久生效）
   ```bash
   echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

4. 登录 GitHub（需要浏览器交互）
   ```bash
   gh auth login
   ```

5. 安装 Copilot 扩展
   ```bash
   gh extension install github/gh-copilot
   ```

### Suggested Action
记录此流程以备后用。后续需要手动完成 gh auth login 步骤（需要浏览器授权）。

### Metadata
- Source: conversation
- Related Files: skills/github-copilot-cli/SKILL.md, skills/github-steipete/SKILL.md
- Tags: github, cli, copilot, macos, installation

---

