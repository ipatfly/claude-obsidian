---
type: concept
title: "Tool Ladder"
address: c-000019
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, architecture, workflow
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Tool Ladder

The Tool Ladder is a 4-level scoping framework created by [[Jake Van Clief]] to determine the minimum necessary complexity required to solve an AI workspace problem. It enforces the philosophy of simplicity: always use the simplest tool that solves the problem.

## The 4 Levels

| Level | Platform | Complexity | Coordination |
|---|---|---|---|
| **Level 1** | Claude Projects | Low | No code, knowledge files upload |
| **Level 2** | Claude Cowork (in-app) | Low-Medium | In-app visual workflow, no local files |
| **Level 3** | VS Code + Claude Code | Medium | Terminal-based agent with local file execution |
| **Level 4** | Custom Front-End UI | High | Dedicated web control surface wrapping Claude Code |

## Key Rules

1. **Anthropic constantly improves the native UI.** Features that required custom Level 4 builds in the past (like Projects or Cowork) are continually absorbed into the default interface.
2. **Always evaluate simple levels first.** Do not jump to Level 4 custom front-ends unless your workflow hits a strict physical limit of Level 3 that cannot be bypassed.

