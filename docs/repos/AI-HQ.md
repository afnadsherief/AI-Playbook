# AI-HQ

## Location
- **Local:** `C:\Projects\AI-HQ`
- **GitHub:** https://github.com/afnadsherief/AI-HQ (private, created 2026-08-08)

## Purpose
"Institutional Headquarters." Explicitly **not** a product repository. A numbered institutional documentation hierarchy covering executive direction, governance, intelligence, execution, delivery, feedback, architecture and decisions.

## System Role
L0 Knowledge � strategic, **non-authoritative** (ADR-0001)

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
- ~~No git remote~~ ✅ **RESOLVED 2026-08-08** — `afnadsherief/AI-HQ` created (private), 9 commits pushed.
- ~~Three-way knowledge-layer overlap~~ ✅ **RESOLVED** by [ADR-0001](../../adr/0001-system-governance.md): AI-Playbook is authoritative; AI-HQ is strategic and non-authoritative. Its `02-Governance/`, `07-Architecture/` and `08-Decisions/` content must be re-scoped or migrated — **deferred, not deleted**.
- Was absent from all prior discovery runs because `C:\Projects\` was outside the declared scan scope.

## Notes
Discovered 2026-08-08 during Phase 1 Run 3 while investigating `C:\Projects\`. Left untouched. Needs an ownership decision against AI-Playbook before either grows further.
