# mcp-sequential-thinking

## Location
- **Local:** `C:\AI\Tools\MCP\mcp-sequential-thinking`
- **GitHub:** https://github.com/afnadsherief/mcp-sequential-thinking (fork created 2026-08-08)
- **Upstream:** https://github.com/arben-adm/mcp-sequential-thinking

## Purpose
Model Context Protocol server that facilitates structured, progressive thinking through defined stages — breaks complex problems into sequential thoughts, tracks progression, and generates summaries.

## System Role
Tooling

## Architecture Summary
Python MCP server cloned from upstream (origin points at `arben-adm/mcp-sequential-thinking`). Single package with a test suite and GitHub Actions workflows.

## Key Modules
- `mcp_sequential_thinking/` — MCP server implementation
- `tests/` — test suite
- `.github/` — CI workflows

## Dependencies
Python, MCP SDK. Declared via `requirements.txt` / `pyproject.toml`. Exact versions UNKNOWN.

## Capabilities (tags)
- mcp
- reasoning
- python
- tooling

## Maturity Level
L3 Production (upstream project)

## Related Systems
- context7 (MCP server)
- codebase-memory-mcp (MCP server)
- github-mcp-server (MCP server)
- ponytail (`ponytail-mcp` sub-package)

## Risks
- Fork created 2026-08-08; `origin` = fork, `upstream` = original. Fork not yet synced or diverged.
- One of five MCP servers in the ecosystem; registration/ownership boundaries undocumented.

## Notes
Read-only vendored reference. Last folder modification 2026-08-06.
