# Requests for Comments (RFC)

Process for proposing and discussing significant engineering changes.

## Overview

RFCs provide a structured process for discussing, refining, and documenting significant engineering decisions before they become standards or architecture decisions.

## RFC Lifecycle

The full lifecycle from idea to standard:

```
┌─────────┐
│  Idea   │
└────┬────┘
     │
     ▼
┌─────────┐
│   RFC   │◄──── Feedback Loop
└────┬────┘
     │
     ▼
┌─────────┐
│  Review │◄──── Stakeholder Discussion
└────┬────┘
     │
     ▼
┌───────────┐
│ Approval  │◄──── Decision Gate
└─────┬─────┘
      │
      ▼
┌─────────┐
│   ADR   │◄──── Document Decision
└────┬────┘
     │
     ▼
┌───────────┐
│ Standard  │◄──── Implementation
└─────┬─────┘
      │
      ▼
┌──────────────┐
│ Institutional │◄──── Adoption & Governance
└──────────────┘
```

### Stage Definitions

| Stage | Description | Entry Criteria | Exit Criteria |
|-------|-------------|----------------|---------------|
| **Idea** | Initial concept or problem identification | Problem identified | Idea documented |
| **RFC** | Formal proposal with solution | Proposal written | RFC submitted |
| **Review** | Community feedback and refinement | RFC open for review | Feedback incorporated or closed |
| **Approval** | Decision gate for acceptance | Review complete | Decision made |
| **ADR** | Formal decision documentation | RFC approved | ADR created |
| **Standard** | Implementation into practice | ADR exists | Standard published |
| **Institutional** | Organizational adoption | Standard exists | Widely adopted |

### Stage Details

#### 1. Idea

The starting point for any change:

- Identify a problem or opportunity
- Initial sketching of potential solutions
- Informal discussion with stakeholders
- Outcome: Documented idea ready for RFC

#### 2. RFC

Formal proposal following the RFC template:

- Problem statement
- Proposed solution
- Alternatives considered
- Trade-offs analyzed
- Recommendation

#### 3. Review

Open discussion period:

- Stakeholder feedback
- Questions and concerns
- Refinement of proposal
- Consensus building

#### 4. Approval

Decision gate:

- Review period concluded
- All concerns addressed or documented
- Formal approval or rejection
- Rationale documented

#### 5. ADR

Architecture Decision Record creation:

- Capture decision rationale
- Document context and constraints
- Record alternatives considered
- Link to RFC

#### 6. Standard

Implementation into practice:

- Publish to Engineering Standards
- Create implementation guidance
- Update related documentation
- Train teams

#### 7. Institutional

Organizational adoption:

- Wide team adoption
- Governance processes established
- Compliance verification
- Continuous improvement

## Maturity in RFC Lifecycle

RFCs track maturity throughout the lifecycle:

| Maturity Level | Definition |
|----------------|------------|
| **Experimental** | Initial proposal, high uncertainty, subject to significant change |
| **Emerging** | Approved in principle, needs validation through implementation |
| **Stable** | Proven through use, minor changes expected |
| **Production** | Fully adopted, changes go through formal process |
| **Institutional** | Core organizational practice, rarely changed |

### Maturity Transitions

```
Experimental → Emerging → Stable → Production → Institutional
     │              │          │          │
     ▼              ▼          ▼          ▼
  "Will this    "Does this    "Is this   "Is this
   work?"        work well?"   reliable?"  essential?"
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
