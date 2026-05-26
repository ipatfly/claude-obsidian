---
type: concept
title: "Remote Sessions"
address: c-000023
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, architecture, remote-work
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Remote Sessions

Remote Sessions allow developers to maintain session persistence and run agentic workspaces (like [[Claude Code]]) across multiple devices, including desktop setups, laptops, and mobile phones.

## Mobile AI Workflows

By setting up remote access to your development server (e.g. via SSH, VS Code Server, or terminal multiplexers like `tmux`):
1. **Session Persistence**: An active agent task can run in the background on your server while you disconnect.
2. **Cross-device handoffs**: Start a build session on your desktop, check the status on your mobile phone via an SSH client (like Termius), and resume on your laptop.
3. **Inbox Integration**: Automate session triggers by parsing incoming emails or webhooks to launch background runs.

