---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Engineering Standards
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Review Standards

Standards for conducting effective code and document reviews.

## Purpose

Ensure reviews are:
- Constructive and respectful
- Focused on quality
- Consistent across teams
- Efficient and timely

## Scope

Applies to:
- Code reviews
- Document reviews
- Architecture reviews
- Design reviews
- Security reviews

## Standards

### 1. Review Principles

#### For Authors

- **Keep PRs small**: Under 400 lines when possible
- **Explain context**: Why is this change needed?
- **Self-review first**: Catch your own issues
- **Be responsive**: Address feedback promptly
- **Accept feedback gracefully**: Not all suggestions are mandatory

#### For Reviewers

- **Be constructive**: Suggest improvements, don't just criticize
- **Be specific**: "Consider extracting this to a function" not "This is bad"
- **Be timely**: Review within 24 hours
- **Be kind**: Remember there's a person on the other side
- **Focus on substance**: Style is secondary to correctness

### 2. What to Review

#### Must Review

- Correctness: Does it work as intended?
- Security: Any vulnerabilities introduced?
- Performance: Any bottlenecks?
- Tests: Are they adequate?
- Documentation: Updated appropriately?

#### Should Review

- Code style: Does it follow conventions?
- Error handling: Are edge cases covered?
- Logging: Is it appropriate?
- Dependencies: Any unnecessary additions?

#### May Review

- Naming choices
- Comment quality
- Formatting details
- Personal preferences

### 3. Comment Conventions

#### Severity Labels

| Label | Meaning | Action Required |
|-------|---------|-----------------|
| `nit:` | Minor style issue | Optional fix |
| `suggestion:` | Consider this | Author's choice |
| `question:` | Unclear point | Needs clarification |
| `blocker:` | Must fix | Required before merge |
| `praise:` | Well done! | Acknowledgment |

#### Comment Examples

```markdown
<!-- Good: Specific with suggestion -->
nit: This variable name is a bit generic. Consider `userId` or `accountId`
to make it clearer what this represents.

<!-- Good: Explaining the concern -->
[security] This input isn't validated. Consider adding:
```javascript
const sanitized = DOMPurify.sanitize(userInput);
```

<!-- Good: Asking for understanding -->
question: Is there a reason we're using a recursive approach here?
An iterative solution might be clearer for future maintainers.

<!-- Good: Blocking issue -->
blocker: This will cause a race condition when multiple requests
come in simultaneously. Need to add locking or use atomic operations.

<!-- Good: Praise -->
praise: Great error handling here! The error messages are clear
and the recovery path is well thought out.
```

### 4. Review Process

```
┌──────────────┐
│ Author opens │
│     PR      │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Auto-checks  │──── Fail ────┐
│ (CI, lint)   │               │
└──────┬───────┘               │
       │ Pass                 │
       ▼                      │
┌──────────────┐               │
│  Reviewers   │               │
│  assigned    │               │
└──────┬───────┘               │
       │                       │
       ▼                       │
┌──────────────┐               │
│  Review      │◄────         │
│  complete    │    │          │
└──────┬───────┘    │          │
       │            │          │
       ▼            │          │
┌──────────────┐    │          │
│  Feedback    │────┘          │
│  addressed?  │               │
└──────┬───────┘               │
       │ Yes                   │
       ▼                      │
┌──────────────┐               │
│   Merged    │               │
└──────────────┘               ▼
                    ┌──────────────┐
                    │   Closed     │
                    │   (revert)   │
                    └──────────────┘
```

### 5. Review Metrics

Track to improve process:

- Time to first review
- Time to merge
- Comments per PR
- Reviewer load distribution
- PR size vs. review depth

## Examples

### Good: Helpful Review

```
Review of PR #123: Add user authentication

Overall: Good work! The implementation is clean and well-tested.
A few suggestions before we merge:

1. [blocker] Line 45: SQL injection vulnerability. 
   Use parameterized query:
   ```sql
   WHERE email = $1  -- Instead of WHERE email = '{{email}}'
   ```

2. [suggestion] The UserService is getting large. Consider
   extracting the password logic into a PasswordHandler class.

3. [nit] Line 89: Typo "succesful" should be "successful"

4. [praise] Excellent test coverage on the happy path!

Let me know when the security issue is fixed and I'll approve.
```

### Bad: Unhelpful Review

```
LGTM.

(Or worse:)

This isn't how I'd do it.

Why didn't you use [favorite technology]?

This is wrong.
```

## Checklist

### For Authors

- [ ] PR description complete
- [ ] Self-review done
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] Breaking changes noted
- [ ] PR size reasonable

### For Reviewers

- [ ] Understanding the change
- [ ] Verifying logic
- [ ] Checking edge cases
- [ ] Reviewing tests
- [ ] Considering security
- [ ] Providing constructive feedback

### For Merging

- [ ] All blockers resolved
- [ ] CI passing
- [ ] At least one approval
- [ ] Review from relevant domain expert
- [ ] Backward compatibility considered

## Anti-Patterns

### 1. Bikeshedding

Focusing on trivial issues:
- "Should have 2 spaces, not 4"
- Line lengths, quote styles
- While ignoring substantive problems

**Solution**: Focus on correctness, security, and maintainability first.

### 2. Gatekeeping

Making unreasonable demands:
- "Rewrite this to use my preferred pattern"
- Blocking for personal preferences
- Never satisfied

**Solution**: Distinguish preferences from requirements.

### 3. Rubber Stamping

Approving without review:
- No actual review
- Creates false confidence
- Defeats the purpose

**Solution**: Take review seriously; actually review.

### 4. Nitpicking Everything

Commenting on every minor style issue:
- Overwhelming to authors
- Obscures important issues
- Slows down reviews

**Solution**: Save nits for automated linters.

### 5. Long PR Reviews

Reviewing massive changes at once:
- Important issues get missed
- Reviewer fatigue
- Slow feedback loop

**Solution**: Keep PRs small; review incrementally.

## Future Improvements

- Implement review metrics dashboard
- Create reviewer rotation system
- Develop review training program
- Add automated review tools
- Establish expert reviewers for domains

## Related Standards

- [04-Coding-Standards](04-Coding-Standards.md) — Code being reviewed
- [12-Pull-Request-Standards](12-Pull-Request-Standards.md) — PR review process
- [07-Definition-of-Done](07-Definition-of-Done.md) — Review completion criteria
