# AI-HQ

## Location
- **Local:** `C:\Projects\AI-HQ`
- **GitHub:** ❌ Not on GitHub — git repository with **no remote configured**

## Purpose
"Institutional Headquarters." Explicitly **not** a product repository. A numbered institutional documentation hierarchy covering executive direction, governance, intelligence, execution, delivery, feedback, architecture and decisions.

## System Role
Knowledge

## Architecture Summary
Documentation-only repository organised as a flat, numbered institutional layer model. Documents carry front-matter (`id`, `title`, `owner`, `layer`, `status`, `lifecycle`) and progress through an approval lifecycle. 8 commits, all "Checkpoint N" governance freezes awaiting executive review.

## Key Modules
- `00-Inbox/` — intake
- `01-Executive/` — Layer 1, vision and direction
- `02-Governance/` — policies and standards
- `03-Intelligence/` — analysis
- `04-Execution/` — execution governance
- `05-Delivery/` — delivery
- `06-Feedback/` — feedback loop
- `07-Architecture/` — architecture
- `08-Decisions/` — decision records
- `09-Templates/` — document templates
- `10-Archive/` — archived material
- `Merlin/` — orchestrator-named area

## Dependencies
None (documentation only).

## Capabilities (tags)
- knowledge
- governance
- documentation
- institutional

## Maturity Level
L2 Active

## Related Systems
- AI-Playbook (knowledge layer — **overlapping mandate**)
- AI-Orchestration (control layer — **overlapping governance mandate**)
- design-intelligence (`Merlin` orchestrator appears in both)

## Risks
- **No git remote** — 8 commits of governance documentation exist only on this machine. Highest data-loss risk in the ecosystem.
- **Three-way knowledge-layer overlap** — AI-HQ, AI-Playbook and AI-Orchestration all claim to own governance, standards, ADRs and architecture. Layer boundaries are undefined between them.
- Was absent from all prior discovery runs because `C:\Projects\` was outside the declared scan scope.

## Notes
Discovered 2026-08-08 during Phase 1 Run 3 while investigating `C:\Projects\`. Left untouched. Needs an ownership decision against AI-Playbook before either grows further.
