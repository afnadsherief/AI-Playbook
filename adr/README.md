# Architecture Decision Records

A collection of significant architectural decisions made during the project lifecycle.

## What is an ADR?

An ADR documents a significant architectural decision along with its context, options considered, and consequences.

## Format

ADRs follow the standard template and include:
- **Status**: Proposed, Accepted, Deprecated, Superseded
- **Context**: Background and constraints
- **Decision**: The chosen approach
- **Consequences**: Benefits and drawbacks

## Index

| ADR | Title | Status |
|---|---|---|
| [0001](./0001-system-governance.md) | System Governance Model | Accepted |
| [0002](./0002-runtime-authority.md) | Runtime Authority | Accepted |
| [0003](./0003-layer-architecture.md) | Canonical Layer Architecture | Accepted |

See `0000-template.md` for the ADR template.

Naming convention: `NNNN-title.md` (e.g., `0001-use-vector-db.md`)

## Authority

Per ADR-0001, **this directory is the only location in the ecosystem where architectural decisions are recorded.** ADRs held in other repositories describe that repository's internal behaviour only and are subordinate to these.
