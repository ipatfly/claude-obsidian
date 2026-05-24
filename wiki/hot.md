---
type: meta
title: "Hot Cache"
updated: 2026-05-24T00:00:00
tags:
  - meta
  - hot-cache
status: evergreen
related:
  - "[[index]]"
  - "[[log]]"
  - "[[Wiki Map]]"
  - "[[getting-started]]"
  - "[[DragonScale Memory]]"
---

# Recent Context

Navigation: [[index]] | [[log]] | [[overview]]

## Last Updated

2026-05-24: Batch ingest of two `_raw/` sources. New concept page [[Interpreted Context Methodology]] (ICM) filed with full architecture notes. New entity pages: [[Jake Van Clief]] (ICM creator), [[ekadetov-llm-wiki]], [[heyitsnoah-claudesidian]], [[jacksteamdev-obsidian-mcp-tools]], [[YuNaga224-obsidian-memory-mcp]]. The four ecosystem entities were gap-fills from the April 8 ingest that missed them. Addresses c-000003 through c-000009 assigned. Counter now at 10.

2026-04-24 (late night): v1.6.0 public release notes shipped. `docs/releases/v1.6.0.md` (Karpathy-style, 346 lines). Three original SVGs at `wiki/meta/dragonscale-{mechanism-overview,6-test-flow,frontier-graph}.svg`. R4 codex verifier ACCEPT WITH FIXES.

2026-04-24 (night): DragonScale end-to-end validation pass. Six-test menu run via Teams orchestration. All six green. First real fold committed. First tiling report (0 errors, 15 review pairs). M4 autoresearch filed 3 new concept pages. v1.6.0 validated.

2026-04-24 (evening): v1.6.0 closeout. `docs/dragonscale-guide.md` (563 lines), release session notes, boundary-frontier artifact, install-guide update. `make test` green (74+ assertions).

## Plugin State

- **Version**: 1.6.0 (all four DragonScale mechanisms shipped and feature-gated)
- **Skills**: 11 (wiki, wiki-ingest, wiki-query, wiki-lint, wiki-fold, save, autoresearch, canvas, defuddle, obsidian-bases, obsidian-markdown)
- **Address counter**: 10 (next to allocate: c-000010)
- **Tests**: `make test` green

## DragonScale Mechanisms

1. **Fold** (M1): `skills/wiki-fold/`; first real fold at `wiki/folds/fold-k3-from-2026-04-23-to-2026-04-24-n8.md`
2. **Addresses** (M2): counter at 10; `c-000001` on DragonScale Memory.md; `c-000002` reserved-unassigned
3. **Tiling lint** (M3): `nomic-embed-text` pulled; first report at `wiki/meta/tiling-report-2026-04-24.md` (0 errors)
4. **Autoresearch** (M4): `scripts/boundary-score.py`; `/autoresearch` surfaces top-5 frontier candidates

## Key Wiki Facts

- 43 pages total, 15 concepts, 13 entities, 2 source summaries
- [[Interpreted Context Methodology]] (ICM): key new concept. Folder structure as agent architecture. Five-layer context loading (Layer 0-4). One agent replaces multi-agent frameworks for sequential pipelines. By [[Jake Van Clief]] / RinDig, 520 stars. Parallels LLM Wiki pattern's hot cache drilldown strategy.
- Ecosystem research (April 8) is now complete: all 16 repos have entity pages or are noted in the comparison matrix.

## Active Threads

- v1.6.0 not yet pushed to GitHub (local commits only, no git tag). User controls push/tag timing.
- CLAUDE.md has one pre-existing uncommitted change ("Release Blog Post" section).
- `flock` not available on macOS; `scripts/allocate-address.sh` fails. Counter managed manually via Bash for this session.

## Repo Locations

- Working: `~/Workspaces/claude-obsidian/`
- Public: https://github.com/AgriciDaniel/claude-obsidian
- Personal fork: https://github.com/ipatfly/claude-obsidian
