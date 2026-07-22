# Requests for Comments (RFC)

Process for proposing and discussing significant engineering changes.

## Overview

RFCs provide a structured process for discussing, refining, and documenting significant engineering decisions before they become standards or architecture decisions.

## RFC Lifecycle

The complete lifecycle from idea to archived:

```
Idea -> Draft -> RFC -> Review -> Prototype -> Approval -> ADR -> Standard -> Production -> Institutional -> Deprecated -> Archived
```

### Lifecycle Stages

| Stage | Purpose | Typical Duration |
|-------|---------|-----------------|
| **Idea** | Initial concept identification | 1-3 days |
| **Draft** | Active development of proposal | 1-2 weeks |
| **RFC** | Formal submission for review | — |
| **Review** | Community feedback period | 1-4 weeks |
| **Prototype** | Implementation validation | 2-8 weeks |
| **Approval** | Decision gate | 1 week |
| **ADR** | Decision documentation | 1-3 days |
| **Standard** | Implementation | varies |
| **Production** | Operational use | ongoing |
| **Institutional** | Organizational norm | ongoing |
| **Deprecated** | Phase-out period | 3-6 months |
| **Archived** | Reference retention | indefinite |

### Stage Details

#### 1. Idea

**Purpose**: Identify and articulate the initial concept.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Problem or opportunity identified |
| Exit Criteria | Concept documented, ready for drafting |
| Typical Duration | 1-3 days |
| Review Requirements | None |
| Artifacts | Brief concept description (1-2 paragraphs) |

#### 2. Draft

**Purpose**: Actively develop the proposal.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Concept documented |
| Exit Criteria | RFC complete and ready for submission |
| Typical Duration | 1-2 weeks |
| Review Requirements | Internal review by author team |
| Artifacts | Draft RFC document |

#### 3. RFC

**Purpose**: Formal submission for community review.

| Aspect | Details |
|--------|---------|
| Entry Criteria | RFC document complete |
| Exit Criteria | RFC submitted via PR |
| Typical Duration | — |
| Review Requirements | PR opened for review |
| Artifacts | RFC document following template |

#### 4. Review

**Purpose**: Gather community feedback and refine proposal.

| Aspect | Details |
|--------|---------|
| Entry Criteria | RFC submitted |
| Exit Criteria | Feedback incorporated, ready for decision |
| Typical Duration | 1-4 weeks |
| Review Requirements | Open feedback period, stakeholder input |
| Artifacts | Updated RFC with feedback incorporated |

#### 5. Prototype

**Purpose**: Validate the proposal through implementation.

| Aspect | Details |
|--------|---------|
| Entry Criteria | RFC approved in principle |
| Exit Criteria | Prototype validates feasibility |
| Typical Duration | 2-8 weeks |
| Review Requirements | Technical validation |
| Artifacts | Working prototype, validation report |

#### 6. Approval

**Purpose**: Formal decision on RFC adoption.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Review complete, prototype validated |
| Exit Criteria | Formal approval or rejection |
| Typical Duration | 1 week |
| Review Requirements | Decision committee or authority |
| Artifacts | Decision with rationale |

#### 7. ADR

**Purpose**: Document the decision for future reference.

| Aspect | Details |
|--------|---------|
| Entry Criteria | RFC approved |
| Exit Criteria | ADR created and merged |
| Typical Duration | 1-3 days |
| Review Requirements | ADR template compliance |
| Artifacts | Architecture Decision Record |

#### 8. Standard

**Purpose**: Publish as formal standard.

| Aspect | Details |
|--------|---------|
| Entry Criteria | ADR created |
| Exit Criteria | Standard published in Engineering Standards |
| Typical Duration | varies |
| Review Requirements | Standards review |
| Artifacts | Published standard, implementation guidance |

#### 9. Production

**Purpose**: Operational deployment and use.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Standard published |
| Exit Criteria | Widely adopted, stable |
| Typical Duration | ongoing |
| Review Requirements | Periodic health checks |
| Artifacts | Usage metrics, adoption reports |

#### 10. Institutional

**Purpose**: Core organizational practice.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Production stable, widely adopted |
| Exit Criteria | Organizational norm established |
| Typical Duration | ongoing |
| Review Requirements | Governance compliance |
| Artifacts | Policy documentation |

#### 11. Deprecated

**Purpose**: Phase out in favor of better alternatives.

| Aspect | Details |
|--------|---------|
| Entry Criteria | New standard supersedes |
| Exit Criteria | No active usage, archived |
| Typical Duration | 3-6 months |
| Review Requirements | Migration verification |
| Artifacts | Deprecation notice, migration guide |

#### 12. Archived

**Purpose**: Retain for historical reference.

| Aspect | Details |
|--------|---------|
| Entry Criteria | Deprecated, no active usage |
| Exit Criteria | Archived permanently |
| Typical Duration | indefinite |
| Review Requirements | None |
| Artifacts | Archived document |

## Engineering Maturity Levels

Complete maturity framework for documents and standards:

| Level | Purpose | Entry Criteria | Exit Criteria | Typical Duration | Review Requirements |
|-------|---------|----------------|---------------|-----------------|-------------------|
| **Draft** | Work in progress | Need identified | Draft complete | 1-2 weeks | Internal only |
| **Experimental** | Proposed, unproven | Proposal written | Validated in prototype | 2-8 weeks | Technical review |
| **Emerging** | Approved, validating | Prototype successful | Proven in production | 1-3 months | Stakeholder review |
| **Stable** | Proven in use | Production validated | Minor changes only | 6-12 months | Periodic review |
| **Production** | Fully adopted | Stable, widely used | Changes go through RFC | ongoing | Governance |
| **Institutional** | Core practice | Organization-wide | Rarely changed | ongoing | Policy-level |
| **Deprecated** | Being phased out | Superseded | Migration complete | 3-6 months | Migration tracking |
| **Archived** | Historical reference | No active usage | Archived | indefinite | None |

### Maturity Definitions

| Level | Definition |
|-------|------------|
| **Draft** | Initial work, unstable, subject to significant change |
| **Experimental** | Proposed but unproven, high uncertainty |
| **Emerging** | Approved in principle, needs validation |
| **Stable** | Proven through use, minor changes expected |
| **Production** | Fully adopted, formal change process |
| **Institutional** | Core organizational practice |
| **Deprecated** | Superseded, do not use for new work |
| **Archived** | Retained for reference, no longer maintained |

### Maturity Transitions

```
Draft -> Experimental -> Emerging -> Stable -> Production -> Institutional
   |         |              |         |           |
   v         v              v         v           v
  "Will    "Does this     "Is this  "Is this    "Is this
   this      work?"         work      reliable?"   essential?"
   make
   sense?"
                                                    |
                                                    v
                                            Deprecated -> Archived
```

## When to Create an RFC

Create an RFC when proposing:

- New Engineering Standards
- Architectural changes affecting multiple teams
- Process changes with significant impact
- Tooling or infrastructure decisions with broad scope
- Changes to existing standards
- Governance framework changes
- Cross-cutting concerns

## RFC Process

### 1. Draft

Write your RFC using the template. Be thorough:
- Clearly define the problem
- Present multiple options
- Analyze trade-offs
- Make a recommendation

### 2. Submit

- Create a PR with your RFC
- Use the naming convention: `NNNN-title.md`
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
- [Glossary](../GLOSSARY.md) — Terminology definitions
- [Terminology](../TERMINOLOGY.md) — Language standards

## Index

See `0000-rfc-template.md` for the RFC template.

Naming convention: `NNNN-title.md` (e.g., `0001-standardized-error-handling.md`)
