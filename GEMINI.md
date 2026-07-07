# WISCI — Context Engineering Framework

You have the WISCI skills available: `/select`, `/write`, `/isolate`, `/compress`, `/commit`.

They manage the `.wisci/` context store in this project:

- `.wisci/context/<topic>.md` — persistent knowledge with a `## References` staleness manifest
- `.wisci/handoff/<stream>.md` — per-work-stream session state (frontmatter: status/updated/goal)
- `.wisci/handoff.md` — script-generated stream index (never edit by hand)
- `.wisci/primer.md` — cached codebase overview

The cycle: `/select` loads validated context at session start → work → `/isolate` researches in isolated windows and persists durable findings via `/write` → `/compress` snapshots work state per stream → `/commit` records AI-layer changes in a `Context:` commit section.

Staleness is computed by the bundled script (requires git + python3): `python3 <plugin>/scripts/wisci.py scan`. Trust its fresh/stale/broken classification — never load stale sections into context.

Dynamic `` !`command` `` lines inside the skills are Claude Code preprocessing; when you see one unexpanded, run that command yourself and use its output.
