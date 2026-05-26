---
type: concept
title: "Product Requirements Document"
address: c-000020
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, specification, agent-builds
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Product Requirements Document (PRD)

A Product Requirements Document (PRD) is a structured Markdown specification that acts as the persistent, stateful context anchor for agent-based code builds. 

## The Stateful Build Loop

When building software with terminal-based agents like [[Claude Code]]:
1. **Never write code immediately.** Have the agent write a PRD first.
2. **Review and edit the PRD.** Verify the phases, tech stack, and scope before any code is generated.
3. **Session-based execution.** Agents run out of tokens and humans run out of energy. Break the build into discrete sessions. The agent reads the PRD at the start of each session, ensuring statefulness and seamless handoffs.

## Reusable PRD Template

```markdown
I want to build [describe what you're building].

Here's my current folder structure and workflow: [paste CLAUDE.md]

Here are repos that do something similar: [paste links]

Make a PRD markdown for Claude Code to read and build from. Include:
- What we're building and why
- Target user (me, for now)
- Existing repos we're pulling from and what we're taking
- Tech stack recommendations
- What features to cut (keep it minimal)
- Phases from MVP to full version
```

