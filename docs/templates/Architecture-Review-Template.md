# Architecture Review Template

Use this template for documenting architecture reviews of AI systems, prompts, or components.

---

## Metadata

| Field | Value |
|-------|-------|
| **Review ID** | `AR-{number}` |
| **Date** | `{YYYY-MM-DD}` |
| **Reviewer(s)** | `{names}` |
| **Author** | `{author}` |
| **Status** | `Draft` / `In Review` / `Approved` / `Rejected` |

---

## Architecture Summary

### What is being reviewed?

Provide a brief description of the system, prompt, or component under review.

### Purpose

Why does this architecture exist? What problem does it solve?

### Scope

What is included in this review? What is explicitly excluded?

### Key Stakeholders

| Role | Name | Responsibility |
|------|------|----------------|
| Owner | | |
| Architect | | |
| Security | | |
| Operations | | |
| Product | | |

---

## Dependencies

### External Dependencies

What external systems, services, or resources does this architecture depend on?

| Dependency | Type | Criticality | Notes |
|------------|------|-------------|-------|
| | API | High/Medium/Low | |
| | Service | High/Medium/Low | |
| | Data | High/Medium/Low | |

### Internal Dependencies

What internal components or systems does this architecture depend on?

| Dependency | Type | Criticality | Notes |
|------------|------|-------------|-------|
| | Component | High/Medium/Low | |
| | Service | High/Medium/Low | |

### Dependency Constraints

Are there any constraints on dependencies (version requirements, availability SLAs, etc.)?

---

## Design Decisions

### Core Design Decisions

What are the key architectural decisions that were made?

| Decision | Rationale | Alternative Considered | Impact |
|----------|-----------|----------------------|--------|
| 1. | | | |
| 2. | | | |
| 3. | | | |

### Design Principles

What principles guided this architecture?

- [ ] **Principle 1**: 
- [ ] **Principle 2**: 
- [ ] **Principle 3**: 

### Patterns Used

What architectural patterns does this architecture employ?

| Pattern | Application | Benefits | Trade-offs |
|---------|-------------|----------|------------|
| | | | |

---

## Trade-offs

### Known Trade-offs

What trade-offs were made in this architecture?

| Trade-off | Chosen Option | Trade-off Description | Mitigation |
|-----------|---------------|---------------------|------------|
| | | | |

### Performance vs. Cost

How does this architecture balance performance requirements against cost?

### Complexity vs. Flexibility

How does this architecture balance complexity against flexibility?

### Latency vs. Quality

How does this architecture balance latency requirements against output quality?

---

## Technical Debt

### Existing Technical Debt

What technical debt exists in this architecture?

| Debt Item | Severity | Impact | Remediation |
|-----------|----------|--------|-------------|
| | High/Medium/Low | | |
| | High/Medium/Low | | |

### Acceptable Debt

What technical debt is explicitly accepted (with justification)?

| Debt Item | Justification | Review Date |
|-----------|---------------|------------|
| | | |

### Debt Remediation Plan

How and when will technical debt be addressed?

---

## Compatibility

### Backward Compatibility

Is this architecture backward compatible with previous versions?

| Aspect | Compatible | Notes |
|--------|------------|-------|
| API | Yes/No/Partial | |
| Data | Yes/No/Partial | |
| Configuration | Yes/No/Partial | |

### Forward Compatibility

Does this architecture support future extensibility?

| Aspect | Supported | Implementation |
|--------|-----------|----------------|
| | | |

### Version Migration

How will existing systems migrate to this architecture?

```
Migration Steps:
1. 
2. 
3. 
```

---

## Migration Strategy

### Pre-Migration Requirements

What must be in place before migration?

- [ ] Requirement 1
- [ ] Requirement 2
- [ ] Requirement 3

### Migration Process

Step-by-step migration process:

| Step | Action | Rollback | Validation |
|------|--------|----------|------------|
| 1. | | | |
| 2. | | | |
| 3. | | | |

### Migration Timeline

| Phase | Date | Milestone |
|-------|------|----------|
| Planning | | |
| Development | | |
| Testing | | |
| Rollout | | |
| Completion | | |

### Rollback Plan

How will the system be rolled back if migration fails?

---

## Risks

### Identified Risks

| Risk | Probability | Impact | Mitigation | Owner |
|------|-------------|--------|------------|-------|
| | High/Med/Low | High/Med/Low | | |
| | High/Med/Low | High/Med/Low | | |

### Risk Acceptance

| Risk | Justification for Acceptance | Approver | Review Date |
|------|----------------------------|----------|-------------|
| | | | |

### Uncertainties

What aspects of the architecture are uncertain or not fully understood?

| Uncertainty | Impact | Resolution Plan |
|-------------|--------|----------------|
| | | |

---

## Future RFCs

### Related RFCs

| RFC | Title | Status | Relationship |
|-----|-------|--------|--------------|
| | | | |

### Planned Enhancements

What future changes or enhancements are anticipated?

| Enhancement | Trigger | Priority |
|-------------|---------|----------|
| | | High/Medium/Low |
| | | High/Medium/Low |

### Deprecation Considerations

What components or patterns will need deprecation?

| Item | Reason | Timeline |
|------|--------|----------|
| | | |

---

## Architectural Principles

### Guiding Principles

What core principles guide this architecture?

| Principle | Description | Application |
|-----------|-------------|-------------|
| **KISS** | Keep it simple, stupid | |
| **DRY** | Don't repeat yourself | |
| **YAGNI** | You aren't gonna need it | |
| **Separation of Concerns** | Modular design | |

### Principles Checklist

- [ ] Each component has a single, well-defined purpose
- [ ] Complexity is justified by clear benefits
- [ ] Dependencies are explicit and minimal
- [ ] Boundaries between components are clear
- [ ] State management is explicit and predictable

---

## Decision Rationale

### Why This Design

Explain the fundamental reasoning behind this architecture.

**Primary Rationale:**

[Explain why this approach was chosen over alternatives]

**Supporting Rationale:**

1. 
2. 
3. 

### Evidence

What evidence supports this decision?

| Evidence Type | Source | Relevance |
|--------------|--------|-----------|
| Performance data | | |
| User research | | |
| Technical analysis | | |
| Industry patterns | | |
| Historical context | | |

### Alternatives Considered

What other approaches were evaluated?

| Alternative | Why Not Chosen | Key Differentiator |
|-------------|----------------|-------------------|
| | | |
| | | |

---

## Known Constraints

### Technical Constraints

What technical limitations affect this architecture?

| Constraint | Impact | Mitigation |
|------------|--------|------------|
| | | |
| | | |

### Resource Constraints

What resource limitations exist?

| Resource | Constraint | Impact |
|----------|------------|--------|
| Budget | | |
| Timeline | | |
| Team Size | | |
| Expertise | | |

### External Constraints

What external factors constrain the design?

| Constraint | Source | Impact |
|------------|--------|--------|
| Regulatory | | |
| Compliance | | |
| Vendor | | |
| Third-party | | |

### Accepted Limitations

What constraints are explicitly accepted?

| Limitation | Justification | Review Date |
|------------|---------------|------------|
| | | |

---

## Future Evolution

### Evolution Trajectory

How is this architecture expected to evolve?

```
Current State -> v1.x -> v2.x -> v3.x
     |             |        |        |
     v             v        v        v
  [current]   [near-term] [mid-term] [long-term]
```

### Planned Extensions

What capabilities are planned for future versions?

| Extension | Priority | Estimated Effort | Dependencies |
|-----------|----------|-----------------|--------------|
| | High/Medium/Low | | |
| | High/Medium/Low | | |

### Scalability Trajectory

How will this architecture scale?

| Scale Dimension | Current | v1.x | v2.x |
|-----------------|---------|-------|-------|
| Users | | | |
| Requests | | | |
| Data | | | |
| Complexity | | | |

### Maintenance Expectations

What ongoing maintenance is required?

| Activity | Frequency | Effort |
|----------|-----------|--------|
| Updates | | |
| Monitoring | | |
| Optimization | | |
| Refactoring | | |

### Sunset Considerations

When and how will this architecture be deprecated?

| Consideration | Plan |
|---------------|------|
| End of life trigger | |
| Deprecation timeline | |
| Migration path | |
| Archival strategy | |

---

## Approval

### Review Checklist

| Criteria | Status | Notes |
|----------|--------|-------|
| Architecture is sound | ✓ / ✗ | |
| Design decisions are documented | ✓ / ✗ | |
| Trade-offs are understood | ✓ / ✗ | |
| Risks are identified and mitigated | ✓ / ✗ | |
| Security concerns addressed | ✓ / ✗ | |
| Performance requirements met | ✓ / ✗ | |
| Migration path is clear | ✓ / ✗ | |
| Documentation is complete | ✓ / ✗ | |

### Approvals

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Owner | | | |
| Architect | | | |
| Security | | | |
| Operations | | | |

### Rejection (if applicable)

| Field | Value |
|-------|-------|
| **Rejected By** | |
| **Rejection Date** | |
| **Reason** | |
| **Required Changes** | |

---

## Notes

### Open Questions

| Question | Owner | Resolution |
|----------|-------|------------|
| | | |

### Discussion Summary

Key points from the review discussion:

1. 
2. 
3. 

### Action Items

| Action | Owner | Due Date | Status |
|--------|-------|----------|--------|
| | | | |
| | | | |

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | | | Initial version |
