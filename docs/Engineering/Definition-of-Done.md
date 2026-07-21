# Definition of Done

Standards for determining when work is complete.

## Purpose

Provide a shared understanding of:
- When a feature is ready for production
- What "done" means across teams
- Quality expectations for all work
- Handoff criteria

## Scope

Applies to:
- All user stories and features
- Bug fixes
- Technical debt
- Infrastructure changes
- Documentation

## Standards

### The Core Checklist

Every item must satisfy:

- [ ] **Code written**: Functionality implemented
- [ ] **Code reviewed**: Peer review completed
- [ ] **Tests written**: Unit tests for new code
- [ ] **Tests passing**: CI pipeline green
- [ ] **Documentation updated**: Docs reflect changes
- [ ] **Deployed to staging**: Tested in environment
- [ ] **Smoke tests passed**: Basic functionality verified
- [ ] **Rollback plan**: Know how to undo if needed

### Type-Specific Criteria

#### User Stories

- [ ] Acceptance criteria met
- [ ] User-facing documentation updated
- [ ] Demo to stakeholders (if required)
- [ ] Analytics/tracking implemented
- [ ] Error states handled

#### Bug Fixes

- [ ] Root cause identified
- [ ] Regression tests added
- [ ] Bug cannot be reproduced
- [ ] Related bugs checked
- [ ] Production monitoring increased

#### Technical Debt

- [ ] Refactoring complete
- [ ] No degradation in coverage
- [ ] Performance baseline maintained
- [ ] API contracts preserved

#### Infrastructure

- [ ] Infrastructure as Code updated
- [ ] Security review completed
- [ ] Cost impact assessed
- [ ] Monitoring configured
- [ ] Runbook created/updated

#### Documentation

- [ ] Content accuracy verified
- [ ] Examples tested
- [ ] Links validated
- [ ] Cross-references updated
- [ ] Localized (if applicable)

## Examples

### Good: Complete Story

```
User Story: Display user profile picture

✓ Code written: Avatar component created with fallback
✓ Code reviewed: Two approvals from frontend team
✓ Tests written: 12 tests covering image, fallback, error states
✓ Tests passing: All 847 tests green
✓ Documentation updated: Component API docs in Storybook
✓ Deployed to staging: Available at staging.example.com
✓ Smoke tests passed: Profile page loads, shows avatars correctly
✓ Rollback plan: Feature flag disabled, reverts to initials

Acceptance criteria:
✓ User sees uploaded photo
✓ User sees initials fallback
✓ User sees placeholder for no photo
✓ Responsive on mobile
```

### Bad: Incomplete Story

```
User Story: Display user profile picture

✓ Code written: Just shows the image URL
✗ Code reviewed: Approved by one person, no real review
✗ Tests written: Only tests happy path
? Tests passing: Can't tell, CI is slow
✗ Documentation: TODO
✗ Deployed to staging: Working locally, probably fine
? Smoke tests: Didn't check
? Rollback plan: What rollback?
```

## Checklist

### Pre-Development

- [ ] Requirements clear
- [ ] Acceptance criteria defined
- [ ] Dependencies identified
- [ ] Effort estimated
- [ ] Priority set

### During Development

- [ ] Test-driven development followed
- [ ] Code follows standards
- [ ] Commits are atomic
- [ ] Branch is current with main

### Pre-Review

- [ ] Self-review completed
- [ ] Tests pass locally
- [ ] No linting errors
- [ ] PR description complete

### Post-Review

- [ ] All comments addressed
- [ ] Reviewer approval obtained
- [ ] CI passing
- [ ] Ready for merge

### Post-Deploy

- [ ] Deployed to production
- [ ] Monitoring verified
- [ ] Smoke tests passed
- [ ] Stakeholders notified
- [ ] Ticket closed

## Anti-Patterns

### 1. Feature-Complete Syndrome

Declaring done when code is written:
- Tests missing
- Documentation absent
- No staging verification

**Solution**: Complete the full checklist every time.

### 2. Gold Plating

Adding unnecessary polish:
- Extra features not requested
- Perfect UI when good enough
- Over-optimization

**Solution**: Meet requirements; add value through quality, not scope creep.

### 3. Shortcut Takers

Skipping important steps:
- "Tests are for other teams"
- "I'll document later"
- "It works on my machine"

**Solution**: No shortcuts; quality is non-negotiable.

### 4. Scope Creep

Uncontrolled feature expansion:
- "While we're at it..."
- Adding nice-to-haves
- Expanding scope mid-sprint

**Solution**: Keep scope fixed; defer additions.

### 5. Handoff Gaps

Assuming someone else will do it:
- "They can finish it"
- "That's ops's problem"
- "The docs team will handle it"

**Solution**: Own your work end-to-end.

## Future Improvements

- Create DoD automation tools
- Integrate DoD into project management
- Track DoD compliance metrics
- Conduct regular DoD retrospectives
- Adjust standards based on team feedback
