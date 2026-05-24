---
type: entity
entity_type: repo
title: "jacksteamdev/obsidian-mcp-tools"
address: c-000008
created: 2026-05-24
updated: 2026-05-24
tags:
  - repo
  - mcp-server
  - ecosystem
status: current
related:
  - "[[claude-obsidian-ecosystem-research]]"
  - "[[claude-obsidian-ecosystem]]"
---

# jacksteamdev/obsidian-mcp-tools

MCP server for Obsidian vault access with semantic search and Templater execution.

**URL**: https://github.com/jacksteamdev/obsidian-mcp-tools
**Category**: MCP Server
**Status**: Seeking maintainers (open until Sep 2025)

## Features

- Vault access via Local REST API plugin
- **Semantic search** via Smart Connections integration
- **Templater execution** — trigger Obsidian templates from AI with dynamic parameters
- SLSA Level 3 binary attestation (reproducible, signed builds)

**Required plugins**: Local REST API + Smart Connections + Templater

## Notable Pattern

Templater execution from AI is the unique capability: allows AI to trigger parameterized Obsidian templates, bridging AI-generated content with Obsidian's native template system. High build-pipeline rigor (SLSA Level 3) unusual for an Obsidian plugin.
