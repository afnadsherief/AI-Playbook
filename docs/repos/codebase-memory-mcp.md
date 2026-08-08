# codebase-memory-mcp

## Location
- **Local:** `C:\AI\Tools\MCP\codebase-memory-mcp`
- **GitHub:** https://github.com/afnadsherief/codebase-memory-mcp
- **Upstream:** https://github.com/DeusData/codebase-memory-mcp

## Purpose
High-performance code intelligence MCP server. Indexes codebases into a persistent knowledge graph — 158 languages, sub-ms queries, 99% fewer tokens. Single static binary, zero dependencies.

## System Role
Tooling

## Architecture Summary
MCP server for code intelligence:
- Codebase indexing into knowledge graph
- 158 language support
- Graph UI for visualization
- Multiple tree-sitter integrations (tree-sitter-form, tree-sitter-magma)
- npm package distribution

## Key Modules
- `graph-ui/` — Graph visualization interface
- `pkg/npm/` — npm distribution
- `tools/tree-sitter-form/` — Tree-sitter form parser
- `tools/tree-sitter-magma/` — Tree-sitter magma parser

## Dependencies
- Rust (static binary)
- Tree-sitter parsers

## Capabilities (tags)
mcp, code-intelligence, knowledge-graph, code-indexing, multi-language

## Maturity Level
L3 Production

## Related Systems
- context7 (similar — documentation vs code intelligence)
- ponytail (skill integration)

## Risks
- Overlap with context7 (documentation indexing vs code intelligence)
- 1982 files — large fork to maintain

## Notes
Fork of DeusData/codebase-memory-mcp. High-performance Rust-based code intelligence.
