---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Review

Systematic evaluation process for prompt quality assurance.

## Purpose

Establish review practices that ensure prompt quality:

- Consistent evaluation criteria
- Multiple perspective reviews
- Clear approval process
- Constructive feedback culture

## Scope

Applies to:

- New prompt development
- Prompt modifications
- Template creation
- Component updates

## Core Principles

### 1. Multiple Perspectives

Review from different viewpoints:

- **Technical**: Correctness, efficiency, implementation
- **Functional**: Accuracy, completeness, usability
- **Security**: Vulnerabilities, injection risks, data handling
- **Business**: Alignment, cost, scalability

### 2. Evidence-Based

Reviews grounded in objective criteria:

- Specific test results
- Measurable quality metrics
- Documented requirements
- Defined acceptance criteria

### 3. Constructive Feedback

Focus on improvement, not criticism:

- Specific observations
- Actionable recommendations
- Acknowledgment of strengths
- Collaborative problem-solving

### 4. Clear Decisions

Definitive outcomes with rationale:

- Approve, Request Changes, or Reject
- Documented reasoning
- Clear next steps
- Defined timeline

## Engineering Standards

### Review Types

| Type | Purpose | Timing | Reviewers |
|------|---------|--------|-----------|
| **Self-Review** | Initial quality check | Before submission | Author |
| **Peer Review** | Technical accuracy | After self-review | 1-2 peers |
| **Security Review** | Risk assessment | Before deployment | Security team |
| **Final Review** | Approval gate | Before release | Owner/Lead |

### Review Criteria

#### Functional Criteria

| Criterion | Assessment | Evidence |
|-----------|------------|----------|
| **Correctness** | Output matches intent | Test results |
| **Completeness** | All requirements met | Requirements checklist |
| **Consistency** | Predictable behavior | Multiple runs |
| **Edge Cases** | Handles boundaries | Edge case tests |

#### Technical Criteria

| Criterion | Assessment | Evidence |
|-----------|------------|----------|
| **Clarity** | Unambiguous language | Readability score |
| **Structure** | Well-organized | Component checklist |
| **Modularity** | Reusable components | Dependency analysis |
| **Performance** | Acceptable latency | Benchmark results |

#### Security Criteria

| Criterion | Assessment | Evidence |
|-----------|------------|----------|
| **Injection Resistance** | No prompt injection | Security tests |
| **Data Handling** | Proper data treatment | Data flow analysis |
| **Output Validation** | Safe outputs | Output tests |
| **Access Control** | Proper authorization | Auth review |

### Review Outcomes

| Outcome | Meaning | Next Step |
|---------|---------|-----------|
| **Approved** | Ready for next stage | Proceed to deployment |
| **Request Changes** | Needs revision | Address feedback |
| **Rejected** | Does not meet standards | Redesign required |
| **Deferred** | Blocked on external issue | Await resolution |

## Workflow

### Review Workflow

```
Submit → Assign → Review → Feedback → Resolve → Approve
```

### Review Process

1. **Submit for Review**
   - Complete self-review checklist
   - Prepare review package
   - Assign reviewers
   - Set timeline

2. **Conduct Review**
   - Reviewer examines prompt
   - Evaluate against criteria
   - Document observations
   - Provide specific feedback

3. **Address Feedback**
   - Author reviews feedback
   - Makes necessary changes
   - Responds to comments
   - Resubmits if needed

4. **Final Approval**
   - Owner reviews resolution
   - Confirms all concerns addressed
   - Grants approval
   - Updates status

### Review Package Contents

```yaml
review_package:
  prompt_id: PRMPT-ORDER-001
  version: v2.1.0
  
  components:
    - prompt_text: prompt.md
    - documentation: docs/
    - tests: tests/
    - changelog: CHANGELOG.md
    - dependencies: dependencies.yaml
  
  self_review:
    completed: true
    checklist_results: self-review-checklist.yaml
    test_results: test-results.yaml
  
  metadata:
    author: author@company.com
    reviewers: [reviewer1@company.com, reviewer2@company.com]
    submitted: 2024-01-15
    deadline: 2024-01-22
```

## Examples

### Review Feedback Format

```markdown
## Review Feedback: PRMPT-ORDER-001 v2.1.0

**Reviewer**: reviewer@company.com
**Date**: 2024-01-18
**Decision**: Request Changes

### Strengths
- Clear component structure
- Comprehensive test coverage
- Good documentation

### Issues

#### Issue 1: Ambiguous Instruction
**Severity**: Medium
**Location**: Instruction Component, line 5
**Observation**: "Extract relevant information" is unclear - what makes information "relevant"?
**Recommendation**: Define relevance criteria explicitly

**Author Response**: Agreed. Will add specific criteria for relevance.

#### Issue 2: Missing Error Handling
**Severity**: High
**Location**: Constraints Component
**Observation**: No handling specified for malformed input
**Recommendation**: Add constraint for invalid input handling

**Author Response**: Will add error handling constraints.

### Required Changes
1. Define "relevant" with specific criteria
2. Add error handling for malformed input
3. Update test cases for edge conditions

### Optional Improvements
- Consider adding confidence thresholds
- Could simplify output format for common cases

### Approval Pending
All required changes addressed and verified.
```

## Checklist

### Self-Review Checklist

- [ ] All required components present
- [ ] Instructions are clear and unambiguous
- [ ] Output format is well-defined
- [ ] Edge cases addressed
- [ ] Tests written and passing
- [ ] Documentation complete
- [ ] Version incremented correctly
- [ ] No security vulnerabilities identified

### Peer Review Checklist

- [ ] Functional requirements met
- [ ] Quality standards achieved
- [ ] Tests adequate and passing
- [ ] Documentation clear and complete
- [ ] No design flaws identified
- [ ] Performance acceptable
- [ ] Feedback provided constructively

### Security Review Checklist

- [ ] Prompt injection attack vectors assessed
- [ ] Input validation implemented
- [ ] Output sanitization defined
- [ ] Data handling practices reviewed
- [ ] Access controls specified
- [ ] Sensitive data protected
- [ ] Security test results reviewed

## Anti-Patterns

### 1. Rubber Stamping

Approving without substantive review:

**Problem**: Quality issues reach production.

**Solution**: Require specific evidence for approval.

### 2. Vague Feedback

General comments without specifics:

**Problem**: Unclear what needs to change.

**Solution**: Require specific observations with evidence.

### 3. Blocking on Minor Issues

Rejecting on trivial matters:

**Problem**: Slow iteration, frustrated teams.

**Solution**: Distinguish blocking vs. non-blocking issues.

### 4. No Security Review

Skipping security assessment:

**Problem**: Vulnerabilities in production.

**Solution**: Mandate security review before deployment.

## Related Documents

- [01-Prompt-Engineering-Overview](01-Prompt-Engineering-Overview.md) — Framework introduction
- [04-Prompt-Lifecycle](04-Prompt-Lifecycle.md) — Lifecycle stages
- [08-Prompt-Testing](08-Prompt-Testing.md) — Testing methodology
- [10-Prompt-Security](10-Prompt-Security.md) — Security considerations

## Future Evolution

- **v1.1**: Automated review checklist tools
- **v1.2**: Review analytics dashboard
- **v1.3**: Collaborative review tools
- **v2.0**: AI-assisted review suggestions
