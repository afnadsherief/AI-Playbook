# browser-use

## Location
- **Local:** `C:\AI\Tools\AI\browser-use`
- **GitHub:** UNKNOWN (no fork under `afnadsherief`)
- **Upstream:** https://github.com/browser-use/browser-use

## Purpose
Third-party Python library enabling AI agents to drive a web browser. Vendored locally as a tooling dependency/reference.

## System Role
Tooling

## Architecture Summary
Python package cloned directly from upstream (origin points at `browser-use/browser-use`, not a personal fork). Standard `pyproject.toml` layout with a library package, CLI entrypoint, examples, docker assets and tests.

## Key Modules
- `browser_use/` — library source
- `bin/` — executables
- `docker/` — container assets
- `examples/` — usage examples
- `skills/` — agent skills
- `scripts/` — utility scripts
- `static/` — static assets
- `tests/` — test suite

## Dependencies
Python (declared in `pyproject.toml`). Exact dependency list UNKNOWN — not read during discovery.

## Capabilities (tags)
- ai-agent
- browser-automation
- python
- tooling

## Maturity Level
L3 Production (upstream project)

## Related Systems
- ponytail (agent skill system)
- AI-Orchestration (potential agent runtime consumer)

## Risks
- Tracks upstream directly — local edits would be lost on pull and cannot be pushed.
- Not forked to `afnadsherief`, so it is absent from the GitHub inventory.
- Requires a Python toolchain that is not guaranteed present on this machine.

## Notes
Read-only vendored reference. Last folder modification 2026-08-07.
