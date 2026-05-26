---
type: concept
title: "Interpreted Context Methodology"
address: c-000005
created: 2026-05-24
updated: 2026-05-26
tags:
  - agent-architecture
  - context-management
  - methodology
  - filesystem
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
related:
  - "[[Jake Van Clief]]"
  - "[[LLM Wiki Pattern]]"
  - "[[DragonScale Memory]]"
  - "[[rindig-interpreted-context-methodology]]"
---

# Interpreted Context Methodology (ICM) v2

**Author**: [[Jake Van Clief]] / RinDig  
**Stars**: 520 (GitHub, 2026)  
**Paper**: arXiv:2603.16021  

The Interpreted Context Methodology (ICM) structures context delivery across a multi-stage workflow by utilizing folder layout and file constraints instead of custom orchestration code.

## The 5-Layer Context Architecture

```
Layer 0: CLAUDE.md           "Where am I?"            Always loaded (~800 tokens)
Layer 1: CONTEXT.md          "Where do I go?"          Read on entry (~300 tokens)
Layer 2: Stage CONTEXT.md    "What do I do?"           Read per-task (~200-500 tokens)
Layer 3: Reference material  "What rules apply?"       Loaded selectively (VOICE.md, DESIGN.md)
Layer 4: Working artifacts   "What am I working with?" Loaded selectively (stage outputs)
```

## Stage Contracts

Each stage defines a `CONTEXT.md` with three pillars:
1. **Inputs**: What files, directories, and sections are needed?
2. **Process**: What is the step-by-step checklist?
3. **Outputs**: What artifacts are generated and where do they go?

## Reusable Bootstrap Files

### 1. `CLAUDE.md` (Layer 0)
Lives in workspace root. Defines identity and core guidelines.
```markdown
# Identity
You are helping [YOUR NAME] with [PROJECT].

# Rules
- Write plain, clear language.
- Ask clarifying questions before assuming.
- When unsure, say so.
```

### 2. `CONTEXT.md` (Layer 1)
Defines project parameters.
```markdown
# Current Project
## What we are building
[Describe in 2-3 sentences]

## What good looks like
[Describe successful output]

## What to avoid
[List common mistakes]
```

## Comparisons & Connections
ICM's layered context loading directly mirrors the hot cache $ightarrow$ index $ightarrow$ domain $ightarrow$ page drilldown in [[wiki-query]]: both prioritize loading the minimum necessary context early to optimize prompt caching and reduce token spend.
