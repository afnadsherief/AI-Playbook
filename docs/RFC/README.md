# Requests for Comments (RFC)

Process for proposing and discussing significant engineering changes.

## Overview

RFCs provide a structured process for discussing, refining, and documenting significant engineering decisions before they become standards or architecture decisions.

## RFC Lifecycle

```
┌─────────┐     ┌─────────┐     ┌──────────┐     ┌─────────┐
│   RFC   │────►│ Review  │────►│ Accepted │────►│   ADR   │────► Standard
└─────────┘     └─────────┘     └──────────┘     └─────────┘
     │               │                │                │
     ▼               ▼                ▼                ▼
 Proposed       Discussion       Finalized        Documented
```

### Stages

| Stage | Description |
|-------|-------------|
| **RFC** | Initial proposal with problem statement and proposed solution |
| **Review** | Open for community feedback and discussion |
| **Accepted** | Approved for implementation or further development |
| **ADR** | Formal Architecture Decision Record created |
| **Standard** | Incorporated into Engineering Standards |

## When to Create an RFC

Create an RFC when proposing:

- New Engineering Standards
- Architectural changes affecting multiple teams
- Process changes with significant impact
- Tooling or infrastructure decisions with broad scope
- Changes to existing standards

## RFC Process

### 1. Draft

Write your RFC using the template. Be thorough:
- Clearly define the problem
- Present multiple options
- Analyze trade-offs
- Make a recommendation

### 2. Submit

- Create a PR with your RFC
- Use the naming convention: `rfc-NNNN-title.md`
- Assign relevant stakeholders as reviewers
- Announce in appropriate channels

### 3. Review

The review period should be:
- Minimum 1 week for non-controversial changes
- 2+ weeks for significant architectural changes
- Open until consensus is reached or concerns are addressed

### 4. Decision

After review:
- **Accepted**: Move to ADR and implementation
- **Rejected**: Document rationale, close RFC
- **Deferred**: Revisit when conditions change
- **Merged**: Combine with related RFCs

## RFC States

| State | Meaning |
|-------|---------|
| Draft | Work in progress, not ready for review |
| Active | Open for discussion |
| Accepted | Approved for implementation |
| Rejected | Declined with rationale |
| Deferred | Postponed indefinitely |
| Superseded | Replaced by another RFC |

## Related Documents

- [ADR Index](../adr/) — Architecture Decision Records
- [Engineering Standards](../Engineering/) — Existing standards
- [Architecture Standards](../Engineering/03-Architecture-Standards.md) — Architecture guidelines

## Index

See `0000-rfc-template.md` for the RFC template.

Naming convention: `NNNN-title.md` (e.g., `0001-standardized-error-handling.md`)
