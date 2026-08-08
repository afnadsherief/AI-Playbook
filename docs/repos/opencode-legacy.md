# opencode (vendored)

## Location
- **Local:** `C:\AI\Tools\AI\opencode`
- **GitHub:** UNKNOWN (no fork under `afnadsherief`)
- **Upstream:** https://github.com/opencode-ai/opencode

## Purpose
Vendored clone of the original `opencode-ai/opencode` CLI agent. Upstream README states the project is **archived** and continued as `charmbracelet/crush`.

**Status: LEGACY (do not delete)**

## System Role
Tooling

## Architecture Summary
Go application, standard layout: `cmd/` entrypoints, `internal/` implementation packages, `scripts/` helpers, GitHub Actions workflows.

## Key Modules
- `cmd/` — CLI entrypoints
- `internal/` — internal packages
- `scripts/` — build/utility scripts
- `.github/` — CI workflows

## Dependencies
Go toolchain. Module dependencies UNKNOWN — `go.mod` not read during discovery.

## Capabilities (tags)
- ai-agent
- cli
- tooling
- go

## Maturity Level
L2 Active (upstream archived)

## Related Systems
- ponytail (`.opencode/` plugin surface)
- AI-Playbook / AI-Orchestration (agent configuration consumers)

## Risks
- **Upstream archived and renamed** — no further development; successor is `charmbracelet/crush`.
- Not the same codebase as the currently used opencode CLI configuration under `~/.config/opencode`; naming collision risk.
- No personal fork — cannot receive local changes.

## Notes
Retained for provenance. Distinct from `C:\AI\.opencode` and `C:\Users\Afnad Sherief\.config\opencode`, which are configuration directories, not repositories.
