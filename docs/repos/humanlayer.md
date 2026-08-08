# humanlayer

## Location
- **Local:** `C:\AI\Tools\AI\humanlayer`
- **GitHub:** https://github.com/afnadsherief/humanlayer
- **Upstream:** https://github.com/humanlayer/humanlayer

## Purpose
Human-in-the-loop AI agent tool — enables AI coding agents to solve hard problems in complex codebases with human oversight and approval workflows.

## System Role
Tooling

## Architecture Summary
Multi-package monorepo:
- React dashboard
- Daemon service
- SDK (TypeScript)
- Contracts package
- Database layer
- Storybook docs
- Linear integration (hack)

## Key Modules
- `apps/daemon/` — Background daemon
- `apps/react/` — React dashboard
- `packages/contracts/` — API contracts
- `packages/database/` — Database layer
- `packages/sdk/` — Client SDK
- `hld/` — HumanLayer daemon (TypeScript SDK)
- `humanlayer-wui/` — Web UI

## Dependencies
- React, TypeScript
- Database (SQLite/Postgres)
- MCP protocol

## Capabilities (tags)
ai-agents, human-in-the-loop, approval-workflows, dashboard, sdk, daemon

## Maturity Level
L3 Production

## Related Systems
- ponytail (skill integration)
- design-intelligence (runtime)

## Risks
- 782 files — large fork
- Complex multi-package maintenance

## Notes
Fork of humanlayer/humanlayer. Provides safety layer for AI agent autonomy.
