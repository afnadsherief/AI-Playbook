# ADR-0001: System Governance Model

- **Status:** Accepted
- **Date:** 2026-08-08
- **Supersedes:** none
- **Related:** [ADR-0002](./0002-runtime-authority.md), [ADR-0003](./0003-layer-architecture.md)

---

## Context

Three repositories independently claimed authority over governance, standards, architecture and decision records:

| Repo | Claim | Evidence |
|---|---|---|
| **AI-Playbook** | "Canonical engineering playbook for all AI products, agents, and platforms" | `README.md`, `docs/Engineering/`, `adr/` |
| **AI-HQ** | "Institutional Headquarters"; owns Governance, Architecture, Decisions layers | `02-Governance/`, `07-Architecture/`, `08-Decisions/` |
| **AI-Orchestration** | Its Knowledge layer "Owns: Documentation, Architecture, ADRs, RFCs, Standards, Prompt Library, AI Playbook" | `docs/architecture.md`, `docs/governance.md`, `docs/adr/`, `docs/standards/`, `playbooks/`, `knowledge/` |

This produced three parallel sets of standards with no precedence rule. A contributor had no way to determine which document governed a given decision, and each repo could contradict the others without detection. AI-Orchestration went further and listed "AI Playbook" as a subordinate asset of its own Knowledge layer — an inversion of the actual relationship.

This is recorded as Conflict #1 and Conflict #6 in `docs/SYSTEM_MAP.md`.

## Decision

**AI-Playbook is the single source of truth for all governance, standards, architecture models, terminology and architectural decisions.**

Authority is assigned as follows:

| Repo | Role | Authority |
|---|---|---|
| **AI-Playbook** | Knowledge (L0) | **Authoritative.** Sole originator of standards, ADRs, terminology, layer models, system rules. |
| **AI-HQ** | Strategic (L0, subordinate) | **Non-authoritative.** May express strategic intent, vision, prioritisation and executive direction. May **not** define standards, ADRs, layer models or architecture. |
| **AI-Orchestration** | Orchestration (L2) | **Execution-only.** Holds no governance authority. Its specifications describe *its own subsystem behaviour only*, and are subordinate to Playbook standards. |

### Rules

1. All standards, ADRs, terminology and architecture models originate **only** from AI-Playbook.
2. No other repository may define governance or architecture standards.
3. A repository may hold documents describing **its own internal behaviour**. It may not generalise those documents into ecosystem-wide standards.
4. Where a subordinate repository's document conflicts with AI-Playbook, **AI-Playbook wins** and the subordinate document must be corrected.
5. Strategic direction from AI-HQ that requires a standards change must be raised as an ADR **in AI-Playbook**.
6. Existing governance documents in subordinate repositories are **not deleted**. They are re-scoped and must carry an authority statement pointing to AI-Playbook.

## Consequences

### Positive
- Eliminates three-way governance duplication; one precedence rule resolves every conflict.
- Contributors have exactly one place to look for a standard.
- Strategy (AI-HQ) and governance (AI-Playbook) are cleanly separated, so strategic churn does not destabilise standards.
- AI-Orchestration's 22 specifications become scoped and coherent rather than competing.

### Negative
- AI-HQ loses formal authority over documents it already carries; its `02-Governance/` and `07-Architecture/` content must be re-scoped or migrated.
- AI-Orchestration's `docs/standards/`, `docs/governance.md` and `docs/adr/` require an authority statement and possible migration.
- Migration is deliberately deferred — this ADR establishes precedence, it does not move files.

### Neutral
- No files were deleted or moved in accepting this ADR. Enforcement is by documented precedence and authority statements.

## Compliance

Enforced by `docs/SYSTEM_RULES.md` rules 15, 16, 19 and 20.
