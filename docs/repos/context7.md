# context7

## Location
- **Local:** `C:\AI\Tools\MCP\context7`
- **GitHub:** https://github.com/afnadsherief/context7
- **Upstream:** https://github.com/upstash/context7

## Purpose
Context7 Platform — up-to-date code documentation for LLMs and AI code editors. MCP server that indexes documentation.

## System Role
Tooling

## Architecture Summary
MCP-based documentation platform:
- CLI tool for doc indexing
- MCP server for AI editor integration
- SDK for programmatic access
- Tools for AI SDK integration

## Key Modules
- `packages/cli/` — Command line interface
- `packages/mcp/` — MCP server
- `packages/sdk/` — Client SDK
- `packages/tools-ai-sdk/` — AI SDK integration tools

## Dependencies
- MCP protocol
- Node.js / TypeScript

## Capabilities (tags)
documentation, mcp, llm-context, code-indexing

## Maturity Level
L3 Production

## Related Systems
- ponytail (skill integration)
- codebase-memory-mcp (similar purpose)

## Risks
- Similar purpose to codebase-memory-mcp — potential overlap

## Notes
Fork of upstash/context7. Provides real-time documentation context to AI editors.
