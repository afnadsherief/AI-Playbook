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
