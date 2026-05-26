---
type: concept
title: "Prompt Engineering"
address: c-000021
created: 2026-05-26
updated: 2026-05-26
tags:
  - concept, prompting, methodology
relevance: core
signal_to_noise: high
verdict: foundational
status: evergreen
---

# Prompt Engineering

Prompt Engineering is the practice of structuring inputs to direct LLM reasoning and coordinate context retrieval. In the Cliefnotes curriculum, prompting works hand-in-hand with folder-based memory.

## Reusable Prompt Structure

Every complex prompt should contain four distinct pillars:
1. **Role**: Who is Claude acting as? (e.g. "You are an expert animator")
2. **Context**: What is the environment? (e.g. "We are working inside a Level 3 workspace")
3. **Task**: What is the exact action to take?
4. **Format**: How should the output be structured? (e.g. Markdown code fences)

## Prompt Sequencing

For complex multi-stage tasks, do not issue a single giant prompt. Sequence them:
* **Stage 1 (Planning)**: Have Claude outline the architecture or PRD.
* **Stage 2 (Verification)**: Review the plan and give steering corrections.
* **Stage 3 (Execution)**: Have Claude write the code or perform the operation.

