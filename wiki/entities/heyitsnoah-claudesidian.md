---
type: entity
entity_type: repo
title: "heyitsnoah/claudesidian"
address: c-000007
created: 2026-05-24
updated: 2026-05-24
tags:
  - repo
  - llm-wiki-pattern
  - ecosystem
  - pkm
status: current
related:
  - "[[claude-obsidian-ecosystem-research]]"
  - "[[LLM Wiki Pattern]]"
  - "[[claude-obsidian-ecosystem]]"
---

# heyitsnoah/claudesidian

Pre-configured Obsidian vault using PARA method with vault adoption and multi-modal research support.

**URL**: https://github.com/heyitsnoah/claudesidian
**Category**: LLM Wiki Pattern (Claude Code plugin)
**Status**: Pre-release kit (stars not tracked)

## Standout Features

- **`/init-bootstrap`** — interactive setup wizard that analyzes an existing vault and imports it safely to `OLD_VAULT/` without destroying current notes
- **Thinking Mode vs Writing Mode** — distinct operating modes for different cognitive tasks
- **Pre-configured commands**: `/thinking-partner`, `/daily-review`, `/research-assistant`, `/weekly-synthesis`, `/inbox-processor`
- **PARA folder structure**: 00_Inbox, 01_Projects, 02_Areas, 03_Resources, 04_Archive
- **Optional integrations**: Gemini Vision for image/video, Firecrawl for web research

## Notable Pattern

Research-and-personalize onboarding: the bootstrap wizard analyzes existing vault content before setup to tailor the wiki structure. Vault migration to `OLD_VAULT/` enables adoption by users with years of existing Obsidian notes without data loss. This is the best vault-adoption approach in the ecosystem.
