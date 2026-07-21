# Pull Request Standards

Standards for creating, reviewing, and merging pull requests.

## Purpose

Enable effective code collaboration through:
- Clear PR descriptions
- Efficient reviews
- Safe merge practices
- Complete documentation

## Scope

Applies to:
- All pull requests
- All contributors
- All repositories

## PR Creation

### 1. Before Creating PR

- [ ] Self-review completed
- [ ] Tests pass locally
- [ ] Linting passes
- [ ] Branch is rebased on main
- [ ] No debug code included
- [ ] No secrets committed

### 2. PR Title

Format: `{type}({scope}): {description}`

```
# Good titles
feat(auth): Add OAuth2 Google login
fix(cart): Prevent negative quantities
docs(api): Update endpoint documentation

# Bad titles
Fixed stuff
WIP
My changes
Updates
```

### 3. PR Description

Use the PR template, but include:

#### What

Explain what this PR does:

```
This PR adds user avatar upload functionality:
- New avatar upload component
- Image processing and storage
- Avatar display in profile
```

#### Why

Explain why this change is needed:

```
Users need to personalize their profiles with photos.
Currently they cannot upload images, reducing engagement.
```

#### How

Explain the approach taken:

```
- Used signed URLs for secure upload
- Stored images in S3 with CDN
- Processed images client-side for preview
```

#### Testing

Document how this was tested:

```
- Unit tests for upload component
- Integration test for full flow
- Manual testing in staging
```

#### Screenshots

For UI changes, include before/after:

```
Before | After
------ | -----
[img]  | [img]
```

### 4. PR Size

| Size | Lines Changed | Recommendation |
|------|---------------|----------------|
| XS | < 50 | Ideal, always welcome |
| S | 50-150 | Good, easy to review |
| M | 150-400 | Acceptable, may need more time |
| L | 400-1000 | Consider splitting |
| XL | > 1000 | Should be split |

#### When to Split

Consider splitting when:
- Multiple independent features
- Separate concerns (frontend/backend)
- Different test strategies
- Multiple reviewers needed

## PR Review

### Reviewer Responsibilities

#### Before Reviewing

- [ ] Understand the context
- [ ] Check related PRs/issues
- [ ] Note any patterns to look for

#### During Review

- [ ] Verify logic is correct
- [ ] Check edge cases
- [ ] Review tests
- [ ] Consider performance
- [ ] Check security
- [ ] Verify documentation

#### Feedback

Be constructive:

```markdown
<!-- Good: Specific with suggestion -->
nit: This variable name is unclear. Consider `maxRetries` 
to make it clear this is a limit.

<!-- Good: Explains the concern -->
[security] This input isn't sanitized. Consider using 
the existing `sanitize()` helper:
```javascript
const safe = sanitize(userInput);
```

<!-- Good: Asking for understanding -->
question: Is there a reason we need to loop here?
An async approach might be clearer.

<!-- Good: Blocking issue -->
blocker: This will cause a race condition under concurrent 
requests. We need to add a mutex or use atomic operations.

<!-- Good: Praise -->
praise: Great error handling here! Very thorough.
```

### Author Responsibilities

When receiving feedback:

- [ ] Respond to all comments
- [ ] Make requested changes
- [ ] Re-request review
- [ ] Resolve threads when fixed
- [ ] Ask for clarification if needed

## PR Merging

### Merge Strategies

| Strategy | Use When |
|----------|----------|
| Squash and merge | Clean history, small PRs |
| Merge commit | Preserving history, larger PRs |
| Rebase and merge | Linear history, maintainer controls |

Choose based on:
- PR size
- Commit quality
- Team preferences
- Repository settings

### Pre-Merge Checklist

- [ ] All checks passing
- [ ] Required approvals obtained
- [ ] No unresolved blocking comments
- [ ] Branch is up to date with main
- [ ] PR description is complete

### Merge Process

```
1. Ensure branch is rebased
   git fetch origin
   git rebase origin/main

2. Run final checks
   npm test
   npm run lint

3. Merge via UI
   - Choose merge strategy
   - Delete branch after merge

4. Verify deployment
   - Check CI/CD pipeline
   - Verify in staging/prod
```

## PR Templates

### Feature PR

```markdown
## Summary
<!-- Brief description of the change -->

## Motivation
<!-- Why is this change needed? -->

## Changes
<!-- What was changed? -->
- 

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update

## Testing
<!-- How was this tested? -->
- [ ] Unit tests added/updated
- [ ] Integration tests added/updated
- [ ] Manual testing completed

## Screenshots
<!-- For UI changes -->

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed self-review
- [ ] I have commented complex code
- [ ] I have updated documentation
- [ ] My changes generate no new warnings
```

### Hotfix PR

```markdown
## Summary
<!-- Brief description of the fix -->

## Type
- [ ] Critical bug
- [ ] Security patch
- [ ] Data fix

## Issue
<!-- Link to issue -->

## Root Cause
<!-- What caused this? -->

## Fix
<!-- How was it fixed? -->

## Testing
<!-- How was fix verified? -->

## Rollback Plan
<!-- How to undo if needed? -->
```

## Communication

### Response Times

| Priority | Expected Response |
|----------|------------------|
| Blocker | Within 2 hours |
| Review request | Within 24 hours |
| Question | Within 48 hours |

### Status Updates

If PR will take longer:

- Update the PR description
- Comment with timeline
- Break into smaller PRs if possible

## Examples

### Good PR

```
Title: feat(profile): Add user avatar upload

## Summary
Implements user avatar upload with image processing,
S3 storage, and CDN delivery.

## Motivation
Users need profile photos for personalization and
social features. Currently limited to Gravatar.

## Changes
- New `AvatarUpload` component with drag-and-drop
- Image processing with Sharp (resize, optimize)
- S3 upload with signed URLs
- Profile display updates

## Type of Change
- [x] New feature

## Testing
- Unit tests for AvatarUpload component (12 tests)
- Integration test for upload flow
- Manual testing in staging with various image types

## Screenshots
[Before: placeholder only]
[After: uploaded avatar displayed]
```

### Bad PR

```
Title: my changes

fixed some stuff
```

## Checklist

### Author Checklist

- [ ] PR follows title format
- [ ] Description is complete
- [ ] Testing documented
- [ ] Screenshots included (if applicable)
- [ ] Breaking changes noted
- [ ] Related issues linked
- [ ] Self-review completed

### Reviewer Checklist

- [ ] Logic is correct
- [ ] Edge cases handled
- [ ] Tests are adequate
- [ ] No security issues
- [ ] Performance acceptable
- [ ] Documentation updated

### Merger Checklist

- [ ] All checks pass
- [ ] Required approvals
- [ ] No unresolved blockers
- [ ] Branch up to date
- [ ] Merge strategy chosen
- [ ] Branch will be deleted

## Anti-Patterns

### 1. Massive PRs

Huge PRs that are impossible to review:
- Important issues missed
- Reviewer fatigue
- Long feedback cycles

**Solution**: Keep PRs small; split large features.

### 2. No Description

PRs without context:
- Reviewers guessing intent
- Wrong assumptions
- Wasted time

**Solution**: Always provide complete description.

### 3. Abandoned PRs

PRs left without updates:
- Stale branches
- Merge conflicts
- Wasted reviewer time

**Solution**: Close quickly or update regularly.

### 4. Review Without Feedback

Approving without real review:
- Quality issues slip through
- False confidence

**Solution**: Actually review; leave feedback or explain approval.

### 5. Nitpick Over Substance

Focusing on style over substance:
- Authors frustrated
- Real issues buried
- Slows velocity

**Solution**: Use linters for style; focus review on substance.

## Future Improvements

- Create PR template generator
- Implement PR size tracking
- Build review assignment system
- Add automated first-response SLAs
- Develop PR analytics dashboard
