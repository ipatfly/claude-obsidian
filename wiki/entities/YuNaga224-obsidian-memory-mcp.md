---
type: entity
entity_type: repo
title: "YuNaga224/obsidian-memory-mcp"
address: c-000009
created: 2026-05-24
updated: 2026-05-24
tags:
  - repo
  - mcp-server
  - memory
  - ecosystem
status: current
related:
  - "[[claude-obsidian-ecosystem-research]]"
  - "[[DragonScale Memory]]"
  - "[[claude-obsidian-ecosystem]]"
---

# YuNaga224/obsidian-memory-mcp

Fork of Anthropic's official memory MCP server, storing AI memories as individual Markdown files visible in Obsidian's graph view.

**URL**: https://github.com/YuNaga224/obsidian-memory-mcp
**Category**: MCP Server

## Features

- Stores AI memories as individual `.md` files (not JSON)
- Uses `[[link]]` syntax — entities appear in Obsidian's graph view
- YAML frontmatter: `entityType`, `created`, `updated`
- Per-entity structure: Observations + Relations sections
- Tools: `create_entities`, `create_relations`, `add_observations`, `search_nodes`, `read_graph`
- Configure via `MEMORY_DIR` env var pointing to any vault folder

## Relation to DragonScale Memory

Both [[DragonScale Memory]] and obsidian-memory-mcp use Markdown files as persistent memory objects with wikilinks for graph connectivity. Key difference: DragonScale is LLM-skill-driven (managed by Claude during sessions); obsidian-memory-mcp is MCP-protocol-driven (external AI agents push memories via the MCP bridge). The two could be run in the same vault without conflict.
