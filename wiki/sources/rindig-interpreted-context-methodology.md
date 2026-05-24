---
type: source
title: "Interpreted Context Methodology"
address: c-000003
created: 2026-05-24
updated: 2026-05-24
tags:
  - research
  - agent-architecture
  - methodology
  - github
status: current
related:
  - "[[Interpreted Context Methodology]]"
  - "[[Jake Van Clief]]"
  - "[[LLM Wiki Pattern]]"
  - "[[DragonScale Memory]]"
raw_file: "_raw/RinDig Interpreted-Context-Methdology.md"
source_url: "https://github.com/RinDig/Interpreted-Context-Methdology"
stars: 520
---

# Source: Interpreted Context Methodology (ICM)

**Type**: GitHub README
**Author**: Jake Van Clief / RinDig
**Stars**: 520
**Date ingested**: 2026-05-24
**Paper**: arXiv:2603.16021

## Summary

ICM replaces framework-level orchestration (CrewAI, LangChain, AutoGen) with filesystem structure. Numbered folders represent pipeline stages; markdown files carry the context that tells a single agent what to do at each step. One agent, reading the right files at the right moment, does the work of multi-agent frameworks without coordination overhead.

The core observation: if prompts and context for each stage already exist as files in a well-organized folder hierarchy, you do not need multiple agents or a coordination framework.

## Pages Created from This Source

- [[Interpreted Context Methodology]] — concept page with full architecture
- [[Jake Van Clief]] — entity page (creator)

## Key Findings

1. **Folder = architecture** — stage sequencing is folder numbering, context scoping is folder hierarchy, state management is files on disk, stage handoffs are one folder's output becoming the next's input
2. **Five-layer context loading** — CLAUDE.md → CONTEXT.md → Stage CONTEXT.md → Reference material → Working artifacts; agents load only what the current stage needs (2,000-8,000 tokens vs 30,000-50,000 monolithic)
3. **Every output is an edit surface** — plain markdown at every stage boundary; humans can inspect and modify before the next stage runs
4. **Glass-box observability** — no logging layer needed; system state is the filesystem
5. **Configure the factory, not the product** — workspace set up once per domain; each run produces a new deliverable using the same configuration
6. **Stage contracts** — each stage CONTEXT.md has explicit Inputs table, Process steps, and Outputs table; no guessing what to load

## Relation to This Vault

ICM and [[LLM Wiki Pattern]] share the core insight that filesystem structure + plain markdown can replace coordination infrastructure. Key difference: ICM is pipeline-execution oriented (sequential stages, per-run artifacts), while the wiki pattern is knowledge-accumulation oriented (compounding, open-ended). ICM's layered context loading directly parallels the hot cache → index → domain → page drilldown in [[wiki-query]].

## Raw File

`_raw/RinDig Interpreted-Context-Methdology.md`
