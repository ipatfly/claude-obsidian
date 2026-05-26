---
type: concept
title: "Cliefnotes Academy"
address: c-000018
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept
  - curriculum
  - cliefnotes
  - agent-architecture
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
related:
  - "[[Interpreted Context Methodology]]"
  - "[[Tool Ladder]]"
  - "[[Product Requirements Document]]"
  - "[[Prompt Engineering]]"
  - "[[Claude Code]]"
  - "[[Remote Sessions]]"
  - "[[Web Animations]]"
  - "[[AI Inbox Automation]]"
---

# Cliefnotes Academy

The Cliefnotes Academy is a training curriculum created by [[Jake Van Clief]] (RinDig) focused on building high-signal personal AI workspaces, local agent environments, and visual implementation playbooks. 

## Curriculum Map

### 1. [[The Foundation]] (11 Lessons)
*Core relevance: core | signal: high | verdict: foundational*
Covers the core [[Interpreted Context Methodology]] (ICM) five-layer context stack, workspace bootstrap (`CLAUDE.md`, `CONTEXT.md`), structured prompting, and local agent orchestration using [[Claude Code]] and [[Claude Desktop]].

### 2. [[Building Your Stack]] (8 Lessons)
*Core relevance: core | signal: high | verdict: foundational*
Focuses on the [[Tool Ladder]] framework for scoping systems, writing detailed [[Product Requirements Document|PRDs]] for agent builds, setting up [[Remote Sessions]] for session persistence, and mobile AI workflows.

### 3. [[Implementation Playbooks]] (11 Lessons)
*Core relevance: secondary | signal: high | verdict: foundational*
Contains operational recipes for transforming Illustrator assets into [[Web Animations]], creating Chrome Extension scraping pipelines, and designing [[AI Inbox Automation]] engines with n8n.

---

## Core System Architecture Principles

1. **Folder Structure as a Design System** — The layout and constraints of the filesystem act as the orchestration framework, replacing heavy third-party code layers.
2. **Context Window Scoping** — Providing only the minimum necessary files per stage to keep token count low and prompt caching optimal.
3. **Stateful Prompting via PRDs** — Maintaining persistent Markdown context documents that the agent reads and writes sequentially across sessions.
