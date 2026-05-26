---
type: concept
title: "Claude Code"
address: c-000022
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, tools, agent-orchestration
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Claude Code

Claude Code is Anthropic's official terminal-based agentic coding tool. It operates natively inside your local filesystem, allowing it to read, write, edit, run commands, execute tests, and manage git repositories.

## Key Modes

* **Interactive Mode**: Standard chat interface for direct command execution and file edits.
* **Plan Mode**: Used for complex multi-file changes where Claude outlines the steps in a checklist before execution.
* **Sub-agent Dispatch**: Claude Code can launch lightweight sub-agents to perform specific research or verification tasks in parallel.

## Operating Rules for Workspace Integration

1. **Bootstrap with CLAUDE.md**: Ensure a valid `CLAUDE.md` is present in the workspace root. Claude Code automatically reads this file at startup.
2. **Limit context size**: Avoid dropping massive raw data directories in the active workspace. Use `.gitignore` or clean directories to keep prompt caching optimal.

