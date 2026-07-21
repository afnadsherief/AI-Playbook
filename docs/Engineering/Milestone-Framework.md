# Milestone Framework

Standards for planning and tracking milestones and releases.

## Purpose

Enable effective milestone planning through:
- Clear milestones with measurable goals
- Predictable delivery cadence
- Transparent progress tracking
- Realistic capacity planning

## Scope

Applies to:
- Sprint planning
- Release planning
- Quarterly objectives
- Technical roadmaps
- Project milestones

## Standards

### 1. Milestone Structure

#### Components

Every milestone should include:

| Component | Description |
|-----------|-------------|
| **Name** | Clear, identifiable title |
| **Goal** | What success looks like |
| **Scope** | What's included/excluded |
| **Timeline** | Start and end dates |
| **Owner** | Single accountable person |
| **Criteria** | Measurable completion criteria |
| **Dependencies** | What it depends on |
| **Risks** | Known risks and mitigations |

#### Milestone Types

| Type | Duration | Purpose |
|------|----------|---------|
| Sprint | 1-2 weeks | Short-cycle delivery |
| Release | 1-3 months | Feature delivery |
| Quarter | 3 months | Business objectives |
| Epic | Varies | Large initiatives |

### 2. Planning Standards

#### Sprint Planning

```
Before Planning:
- Backlog groomed
- Estimates ready
- Dependencies identified

During Planning:
- Select highest priority items
- Commit to achievable scope
- Identify blockers early
- Assign owners

After Planning:
- Sprint goal defined
- Commitments documented
- Communication sent
```

#### Capacity Planning

Calculate available capacity:

```
Team Capacity = Team Members × Days × (1 - PTO%) × (1 - Meeting%)

Example:
5 engineers × 10 days × 0.9 × 0.75 = 33.75 person-days

Buffer for unexpected work: 20%
Available capacity: 33.75 × 0.8 = 27 person-days
```

### 3. Tracking Progress

#### Metrics

| Metric | Frequency | Purpose |
|--------|-----------|---------|
| Velocity | Weekly | Predict capacity |
| Burndown | Daily | Track progress |
| Blockers | Daily | Identify impediments |
| Scope changes | Weekly | Track changes |

#### Progress Updates

Regular communication cadence:

```
Daily: Standup updates (blockers, progress)
Weekly: Sprint review + retrospective
Monthly: Milestone health check
Quarterly: Roadmap review
```

### 4. Milestone Reviews

#### Review Agenda

1. Review goals vs. actuals
2. Analyze scope changes
3. Identify blockers encountered
4. Capture learnings
5. Document carry-overs
6. Celebrate wins

#### Retrospective Questions

- What went well?
- What could be improved?
- What will we do differently?
- Any systemic issues to address?

## Examples

### Good: Well-Defined Milestone

```markdown
## Milestone: User Authentication V2

**Timeline:** 2024-Q1 (Jan 15 - Mar 31)
**Owner:** Sarah Chen
**Team:** Platform (4 engineers)

### Goal
Replace legacy authentication with modern, secure
implementation supporting SSO, MFA, and improved UX.

### Scope
✓ SSO integration (SAML, OAuth)
✓ MFA support (TOTP, SMS backup)
✓ Password policy enforcement
✓ Session management
✓ Login flow redesign
✗ Account recovery (deferred to Q2)
✗ Password reset flow redesign

### Success Criteria
- 95% of users can authenticate successfully
- Auth latency < 500ms p99
- Zero auth-related security incidents
- Support ticket reduction > 30%

### Dependencies
- Identity provider: IT team (blocking)
- Design mocks: Design team (blocking)
- Security review: Security team (in parallel)

### Risks
| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| IDP delays | Medium | High | Weekly check-ins |
| Migration complexity | High | Medium | Pilot with small group |
| User adoption | Low | High | Training materials |
```

### Bad: Vague Milestone

```
Milestone: Improve stuff

We'll do some things to make things better.
Jane will work on it. Target is sometime this quarter.
```

## Checklist

### Milestone Creation

- [ ] Goal clearly defined
- [ ] Scope documented
- [ ] Timeline realistic
- [ ] Owner assigned
- [ ] Dependencies identified
- [ ] Risks assessed
- [ ] Criteria measurable

### Milestone Execution

- [ ] Daily standups
- [ ] Weekly progress reviews
- [ ] Blockers escalated promptly
- [ ] Scope protected
- [ ] Stakeholders updated

### Milestone Completion

- [ ] All criteria met
- [ ] Review conducted
- [ ] Learnings documented
- [ ] Celebrations shared
- [ ] Handoffs completed

## Anti-Patterns

### 1. Scope Creep

Expanding scope without adjustment:
- "Just one more small thing"
- Moving goalposts
- Timeline not extended

**Solution**: Formal change control; scope vs. timeline trade-off.

### 2. Multi-Tasking Overload

Too many concurrent milestones:
- Context switching
- Quality suffers
- Nothing gets attention

**Solution**: Limit WIP; serialize when possible.

### 3. Perfectionism

Endless polish before release:
- Feature never ships
- Value never delivered
- Team frustrated

**Solution**: Define "good enough"; iterate.

### 4. Hero Culture

Relying on individuals:
- Burnout
- Knowledge silos
- Single point of failure

**Solution**: Distribute work; collective ownership.

### 5. Plan-Following

Blind adherence to plan:
- Ignoring feedback
- Missing opportunities
- Persisting with failures

**Solution**: Adapt plan based on learnings.

## Future Improvements

- Create milestone tracking templates
- Automate progress reporting
- Build milestone analytics
- Develop capacity planning tools
- Establish milestone templates for common types
