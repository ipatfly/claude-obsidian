# claude-obsidian — Claude + Obsidian Wiki Vault

This folder is both a Claude Code plugin and an Obsidian vault.

**Plugin name:** `claude-obsidian`
**Skills:** `/wiki`, `/wiki-ingest`, `/wiki-query`, `/wiki-lint`
**Vault path:** This directory (open in Obsidian directly)

## What This Vault Is For

This vault demonstrates the LLM Wiki pattern — a persistent, compounding knowledge base for Claude + Obsidian. Drop any source, ask any question, and the wiki grows richer with every session.

## Vault Structure

```
_raw/           source documents — immutable, Claude reads but never modifies
wiki/           Claude-generated knowledge base
.claude/        active workspace configuration (source of truth)
  skills/       active skills (invoked by Claude Code/Gemini CLI)
  agents/       active agents (loaded by Claude Code/Gemini CLI)
  memory/       project memory and context
_system/        system backend — scripts, setup tools, tests
  bin/          one-time setup scripts (setup-vault, setup-dragonscale, setup-multi-agent)
  scripts/      DragonScale runtime helpers (invoked by skills at session time)
  tests/        unit tests for scripts
_templates/     Obsidian Templater templates
_attachments/   images and PDFs referenced by wiki pages
```

## How to Use

Drop a source file into `_raw/`, then tell Claude: "ingest [filename]".

Ask any question. Claude reads the index first, then drills into relevant pages.

Run `/wiki` to scaffold a new vault or check setup status.

Run "lint the wiki" every 10-15 ingests to catch orphans and gaps.

## Cross-Project Access

To reference this wiki from another Claude Code project, add to that project's CLAUDE.md:

```markdown
## Wiki Knowledge Base
Path: /path/to/this/vault

When you need context not already in this project:
1. Read wiki/hot.md first (recent context, ~500 words)
2. If not enough, read wiki/index.md
3. If you need domain specifics, read wiki/<domain>/_index.md
4. Only then read individual wiki pages

Do NOT read the wiki for general coding questions or things already in this project.
```

## Plugin Skills

| Skill | Trigger |
|-------|---------|
| `/wiki` | Setup, scaffold, route to sub-skills |
| `ingest [source]` | Single or batch source ingestion |
| `query: [question]` | Answer from wiki content |
| `lint the wiki` | Health check |
| `/save` | File the current conversation as a structured wiki note |
| `/autoresearch [topic]` | Autonomous research loop: search, fetch, synthesize, file |
| `/canvas` | Visual layer: add images, PDFs, notes to Obsidian canvas |

## MCP

The Local REST API and MCP server are configured for your use in Obsidian. Always check if the MCP server is currently running and reachable. If it is not running, nudge Patrick: "To be able to use your MCP server you need to start Obsidian."

See `.claude/skills/wiki/references/mcp-setup.md` for detailed setup and configuration instructions.

## Personal Setup (ipatfly)

This is a personal fork. Origin: `https://github.com/ipatfly/claude-obsidian`
Upstream: `https://github.com/AgriciDaniel/claude-obsidian`

Wiki demo content kept as reference.

## Memory

Project memory lives at `.claude/memory/`. Read `.claude/memory/MEMORY.md` at session start
for project context.
