# AI-Playbook

## Location
- **Local:** `C:\AI\AI-Playbook`
- **GitHub:** https://github.com/afnadsherief/AI-Playbook

## Purpose
Canonical engineering playbook and knowledge base for all AI products, agents, and platforms. Single source of truth for system documentation, standards, and repo intelligence.

## System Role
Knowledge

## Architecture Summary
Documentation-first repository:
- **docs/Engineering/** — 12 engineering standards (typescript through git-workflow)
- **docs/Prompt-Engineering/** — 13 prompt engineering guides
- **docs/RFC/** — RFC template + prompt contracts + observability
- **docs/templates/** — Architecture review template
- **docs/repos/** — Per-repo intelligence (Phase 1 addition)
- **adr/** — Architecture decision records
- **knowledge/** — Concepts, patterns, techniques
- **agents/** — Agent definitions
- **prompts/** — Prompt templates

## Key Modules
- `docs/Engineering/` — engineering standards
- `docs/Prompt-Engineering/` — prompt engineering
- `docs/repos/` — repo intelligence files
- `docs/REGISTRY.md` — master system registry
- `docs/SYSTEM_RULES.md` — ecosystem rules
- `docs/AUDIT_FINDINGS.md` — drift and duplication analysis

## Dependencies
- AI-Orchestration (control layer)
- design-intelligence (runtime)

## Capabilities (tags)
knowledge, documentation, standards, engineering, prompts, architecture

## Maturity Level
L2 Active

## Related Systems
- AI-Orchestration (control)
- design-intelligence (runtime)

## Risks
- Was in "Bootstrap" state before Phase 1
- Does not yet reflect actual system state (being fixed)

## Notes
This is the target repo for Phase 1 alignment. All repo intelligence flows here.
