# codex-plugins (untracked clone)

## Location
- **Local:** `C:\Users\Afnad Sherief\.codex\.tmp\plugins`
- **GitHub:** UNKNOWN (no `origin` remote configured)

## Purpose
Curated collection of Codex plugin examples. Each plugin lives under `plugins/<name>/` with a required `.codex-plugin/plugin.json` manifest plus optional `skills/`, `.app.json`, `.mcp.json`, `agents/` and `commands/` surfaces.

## System Role
Tooling

## Architecture Summary
Git repository with no remote, checked out inside a temporary Codex cache directory. Flat plugin catalogue driven by per-plugin manifests.

## Key Modules
- `plugins/` — plugin catalogue
- `.agents/` — agent definitions
- `README.md` — plugin authoring guide

## Dependencies
UNKNOWN — no manifest inspected.

## Capabilities (tags)
- plugins
- ai-agent
- tooling

## Maturity Level
L1 Prototype (local, unowned)

## Related Systems
- ponytail (`.codex-plugin/` surface)
- AI-Orchestration (`.codex/` config)

## Risks
- **No git remote** — content exists only on this machine; unrecoverable if the temp directory is cleared.
- Lives under `.codex\.tmp\` — a cache path that tooling may delete without warning.
- Ownership and provenance UNKNOWN.

## Notes
Last modified 2026-07-22. Included for completeness; not moved or altered.
