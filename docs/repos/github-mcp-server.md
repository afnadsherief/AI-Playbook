# github-mcp-server

## Location
- **Local:** `C:\AI\Tools\MCP\github-mcp-server`
- **GitHub:** https://github.com/afnadsherief/github-mcp-server
- **Upstream:** https://github.com/github/github-mcp-server

## Purpose
GitHub's official MCP Server — provides AI agents with GitHub API access (issues, PRs, CI, code review, etc.).

## System Role
Tooling

## Architecture Summary
Official GitHub MCP server:
- GitHub API integration via MCP protocol
- Issue/PR management
- CI/CD status monitoring
- Code review automation
- Webhook handling

## Key Modules
- `src/` — MCP server implementation
- `ui/` — Optional web UI

## Dependencies
- GitHub API
- MCP protocol
- Node.js / TypeScript

## Capabilities (tags)
mcp, github, issues, pr, ci-cd, code-review, automation

## Maturity Level
L3 Production

## Related Systems
- github.com (API source)
- ponytail (skill integration)

## Risks
- Upstream changes require sync
- GitHub API rate limits

## Notes
Fork of github/github-mcp-server. Critical for AI-driven GitHub automation.
