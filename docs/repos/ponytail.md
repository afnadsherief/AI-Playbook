# ponytail

## Location
- **Local:** `C:\AI\Skills\ponytail`
- **GitHub:** https://github.com/afnadsherief/ponytail

## Purpose
Ponytail skill system — provides AI skills/plugins for various editors (Claude, Codex, Cursor, Devin, Kiro, OpenClaw, OpenCode, Qoder, Windsurf). Benchmark and testing infrastructure included.

## System Role
Tooling

## Architecture Summary
Multi-platform skill/plugin system:
- Editor plugins (Claude, Codex, Cursor, Devin, Kiro, OpenClaw, OpenCode, Qoder, Windsurf)
- Benchmark + testing infrastructure
- MCP server integration
- PI extension

## Key Modules
- `.claude-plugin/` — Claude plugin config
- `.codex-plugin/` — Codex plugin
- `.cursor/` — Cursor rules
- `.devin-plugin/` — Devin plugin
- `.kiro/` — Kiro config
- `.openclaw/` — OpenClaw config
- `.opencode/` — OpenCode config
- `.qoder/` + `.qoder-plugin/` — Qoder configs
- `.windsurf/` — Windsurf config
- `benchmarks/` — Performance benchmarks
- `commands/` — Skill commands
- `docs/` — Documentation
- `hooks/` — Git hooks
- `pi-extension/` — PI extension
- `ponytail-mcp/` — MCP server
- `scripts/` — Utility scripts
- `skills/` — Skill definitions
- `tests/` — Test suite

## Dependencies
- Multiple AI editor platforms

## Capabilities (tags)
skills, plugins, editors, mcp, benchmarks, multi-platform

## Maturity Level
L3 Production

## Related Systems
- design-intelligence (runtime)
- AI-Orchestration (control)

## Risks
- Complex multi-platform maintenance
- Plugin format changes from upstream editors

## Notes
Critical infrastructure — provides skills used across all editing environments.
