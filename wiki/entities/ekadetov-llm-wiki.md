---
type: entity
entity_type: repo
title: "ekadetov/llm-wiki"
address: c-000006
created: 2026-05-24
updated: 2026-05-24
tags:
  - repo
  - llm-wiki-pattern
  - ecosystem
status: current
related:
  - "[[claude-obsidian-ecosystem-research]]"
  - "[[LLM Wiki Pattern]]"
  - "[[claude-obsidian-ecosystem]]"
---

# ekadetov/llm-wiki

LLM Wiki Pattern plugin with hybrid search and multi-wiki support.

**URL**: https://github.com/ekadetov/llm-wiki
**Category**: LLM Wiki Pattern (Claude Code plugin)
**Prerequisites**: Node 18+, Git, Obsidian vault at `~/ObsidianVault/`

## Standout Features

- **qmd hybrid search** (BM25 + vector) — auto-installed via SessionStart hook; significant quality improvement over keyword/index for large vaults
- **Multi-wiki support** — `/llm-wiki:wiki init <topic-name>` creates isolated topic wikis; `/llm-wiki:wiki remove <topic>` removes cleanly
- **URL ingestion** — pass `https://` URLs directly to the ingest command
- **Auto-commit on every ingest** via git
- **Marp presentation output**

## Notable Pattern

BM25 + vector hybrid search as the retrieval layer is the most technically sophisticated search approach in the ecosystem. Auto-install via SessionStart keeps the Node dependency invisible to the user. Multi-wiki isolation (one wiki per topic) is a distinct architecture from the single-vault approach in claude-obsidian.
