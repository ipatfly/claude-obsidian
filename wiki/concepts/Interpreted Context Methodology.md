---
type: concept
title: "Interpreted Context Methodology"
address: c-000005
created: 2026-05-24
updated: 2026-05-24
tags:
  - agent-architecture
  - context-management
  - methodology
  - filesystem
status: developing
related:
  - "[[Jake Van Clief]]"
  - "[[LLM Wiki Pattern]]"
  - "[[DragonScale Memory]]"
  - "[[rindig-interpreted-context-methodology]]"
---

# Interpreted Context Methodology (ICM)

**Author**: [[Jake Van Clief]] / RinDig
**Stars**: 520 (GitHub, 2026)
**Paper**: arXiv:2603.16021

Folder structure as agent architecture. ICM replaces framework-level orchestration with filesystem layout. One agent reads the right files at the right moment; the folder structure tells it what to do at each step.

> "If the prompts and context for each stage of a workflow already exist as files in a well-organized folder hierarchy, you do not need multiple agents or a coordination framework."

## Core Mechanism

The filesystem does the work that frameworks do in code:

| Framework concern | ICM equivalent |
|-------------------|----------------|
| Stage sequencing | Folder numbering (`01-research/`, `02-script/`) |
| Context scoping | Folder hierarchy |
| State management | Files on disk |
| Stage handoffs | One folder's `output/` is the next folder's input |

## Five-Layer Context Architecture

```
Layer 0: CLAUDE.md           "Where am I?"            Always loaded (~800 tokens)
Layer 1: CONTEXT.md          "Where do I go?"          Read on entry (~300 tokens)
Layer 2: Stage CONTEXT.md    "What do I do?"           Read per-task (~200-500 tokens)
Layer 3: Reference material  "What rules apply?"       Loaded selectively
Layer 4: Working artifacts   "What am I working with?" Loaded selectively
```

**Layer 3 vs Layer 4**: Layer 3 is stable factory config (design systems, voice rules, domain conventions). Layer 4 is run-specific input (previous stage output, user-provided material). A rendering agent may only need layers 0-2. A script-writing agent reads to layer 4. Total context per stage: 2,000-8,000 tokens vs 30,000-50,000 monolithic.

## Stage Contracts

Each stage defines a `CONTEXT.md` with three parts:

```
## Inputs
| Source | File/Location | Section/Scope | Why |

## Process
1. Step one
2. Step two

## Outputs
| Artifact | Location | Format |
```

Creative stages also add **checkpoints** (human steering pauses) and **audits** (quality checklists before writing output).

## Design Principles

1. **One stage, one job** — a stage that researches does not also write (Unix single responsibility)
2. **Plain text as interface** — markdown files; any tool that reads text can participate
3. **Layered context loading** — load only what the current stage needs (prevention, not compression)
4. **Every output is an edit surface** — humans can modify between stages; next stage reads whatever was left
5. **Configure the factory, not the product** — workspace configured once; each run produces a new deliverable with same config

## Workspace Layout

```
workspace/
  CONTEXT.md               # Layer 1: task routing
  stages/
    01-research/
      CONTEXT.md            # Layer 2: stage contract
      references/           # Layer 3: stable reference material
      output/               # Layer 4: working artifacts (handoff point)
    02-script/
      ...
  _config/                  # Layer 3: brand, voice, design system
  shared/                   # Layer 3: cross-stage resources
  setup/
    questionnaire.md        # One-time onboarding (flat, system-level only)
```

## Observability

The system is glass-box by design: every intermediate output is a plain file. No logging layer needed. To debug stage N, open the folder and read the files. Stage state is filesystem state.

## Where ICM Works

Sequential multi-step workflows with human review at each stage: content production, research, analysis, monitoring/digest, reporting, training material development.

Common thread: sequential (step 2 follows step 1), reviewable (human checks each step), repeatable (same pipeline with different input each run).

## Where ICM Does Not Work

- **Real-time multi-agent collaboration** — file-based handoffs are too slow for tight agent loops requiring message-passing infrastructure
- **High-concurrency systems** — needs queueing, state isolation, deployment; ICM is local-first
- **Complex automated branching** — human branching between stages is fine; automated branching pushes ICM toward becoming a framework

## ICM vs MCP

MCP standardizes how models access external tools and data (the integration problem). ICM structures context delivery across a multi-stage workflow. Complementary: an ICM stage might use MCP connections while folder structure determines what context the agent receives.

## ICM vs LLM Wiki Pattern

| Aspect | ICM | [[LLM Wiki Pattern]] |
|--------|-----|---------------------|
| Focus | Pipeline execution | Knowledge accumulation |
| Persistence | Per-run artifacts | Compounding wiki |
| Structure | Fixed numbered stages | Open-ended ingest/query |
| Human role | Review at stage boundaries | Curate sources, ask questions |
| Context strategy | Stop at needed layer | Hot cache → index → page drilldown |
| Token profile | 2,000-8,000 per stage | ~500 hot cache + drill-in |

ICM's layered context loading parallels the hot cache → index → domain → page drilldown in [[wiki-query]]: both strategies load minimum necessary context and stop early.

## Available Workspaces (in the repo)

| Workspace | Stages | Output |
|-----------|--------|--------|
| script-to-animation | 3 | Script + animation spec + Remotion code |
| course-deck-production | 5 | PowerPoint slide deck from unstructured material |
| workspace-builder | 5 | New ICM workspace for any domain |
