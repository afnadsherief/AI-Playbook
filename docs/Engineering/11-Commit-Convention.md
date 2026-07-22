---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Version Control
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Commit Convention

Standards for writing clear, consistent commit messages.

## Purpose

Enable:
- Clear change history
- Automated changelog generation
- Effective code review
- Semantic versioning

## Scope

Applies to:
- All Git commits
- All repositories
- All contributors

## Format

### Structure

```
{type}({scope}): {description}

[optional body]

[optional footer(s)]
```

### Components

| Component | Description | Required |
|-----------|-------------|----------|
| `type` | Kind of change | Yes |
| `scope` | Affected area | Optional |
| `description` | Brief summary | Yes |
| `body` | Detailed explanation | Optional |
| `footer` | Breaking changes, issues | Optional |

### Types

| Type | Description |
|------|-------------|
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation only |
| `style` | Formatting, no code change |
| `refactor` | Code change, no feature/fix |
| `perf` | Performance improvement |
| `test` | Adding/updating tests |
| `build` | Build system changes |
| `ci` | CI/CD changes |
| `chore` | Maintenance tasks |
| `revert` | Reverting a commit |

### Scopes

Common scopes (customize per project):

| Scope | Usage |
|-------|-------|
| `api` | API endpoints |
| `auth` | Authentication |
| `db` | Database |
| `ui` | User interface |
| `core` | Core functionality |
| `config` | Configuration |
| `deps` | Dependencies |
| `docs` | Documentation |
| `tests` | Test files |

## Examples

### Good Commits

```bash
# Feature
git commit -m "feat(auth): Add OAuth2 Google login"

# Bug fix
git commit -m "fix(cart): Prevent negative quantities"

# Documentation
git commit -m "docs(api): Update user endpoint examples"

# Refactoring
git commit -m "refactor(payment): Extract payment processor"

# Breaking change
git commit -m "feat(api)!: Change response format

BREAKING CHANGE: User endpoint now returns object instead of array.
Migrate by accessing response.users instead of response[0]."

# Issue reference
git commit -m "fix(ui): Correct button alignment

Fixes #123
Closes #124"
```

### Bad Commits

```bash
# Too vague
git commit -m "Fixed stuff"
git commit -m "Updates"
git commit -m "WIP"

# Missing context
git commit -m "Changed file"

# Wrong type
git commit -m "Added feature"  # Should be "feat"

# Too long
git commit -m "This commit adds the ability to export user data to CSV format with headers and proper escaping for special characters"

# Includes irrelevant changes
git commit -m "Fix bug and refactor unrelated code"
```

## Commit Message Guidelines

### Do

- Use imperative mood: "Add feature" not "Added feature"
- Keep subject line under 72 characters
- Use lowercase for type and scope
- Reference issues and PRs in footer
- Explain *why*, not just *what*

### Don't

- Don't end subject line with period
- Don't use "and" in subject (separate commits)
- Don't use filler words (just, only, etc.)
- Don't capitalize scope names

## Detailed Guidelines

### Subject Line

```
# Good
feat(api): Add user profile endpoint

# Bad - period at end
feat(api): Add user profile endpoint.

# Bad - caps
feat(API): Add User Profile Endpoint

# Bad - wrong mood
feat(api): Added user profile endpoint

# Bad - too long
feat(api): Added the new endpoint for getting user profiles with all their associated data including preferences and settings
```

### Body

Use body for explaining what and why, not how:

```
Add rate limiting to API endpoints

- Prevent abuse from automated clients
- Protect system during high traffic
- Per-user and per-IP limits

Fixes #456
```

### Breaking Changes

```
perf(api)!: Increase default timeout

BREAKING CHANGE: Default request timeout changed from 30s to 60s.
Update client configurations if relying on 30s default.

Migration:
1. Update client timeout settings
2. Adjust circuit breaker thresholds
```

### Reverts

```
revert: "feat(auth): Add password reset flow"

This reverts commit abc123def456.

Reason: Security vulnerability in reset token generation.
```

## Automation

### Commit Message Validation

Use commitlint:

```yaml
# .commitlintrc.yml
rules:
  type-enum:
    - always
    - [feat, fix, docs, style, refactor, perf, test, build, ci, chore, revert]
  type-case:
    - always
    - lower-case
  subject-case:
    - never
    - [sentence-case, pascal-case, start-case]
  subject-empty:
    - never
  subject-full-stop:
    - never
  header-max-length:
    - always
    - 72
```

### Pre-commit Hook

```yaml
# .pre-commit-config.yml
repos:
  - repo: https://github.com/conventional-changelog/commitlint
    revs:
      - '@master'
    hooks:
      - id: commitlint
        stages: [commit-msg]
        args: ['--config', '.commitlintrc.yml']
```

## Examples by Type

### feat

```
feat(registration): Add multi-step registration form

- Step 1: Basic info (email, password)
- Step 2: Profile details (name, avatar)
- Step 3: Preferences

Closes #789
```

### fix

```
fix(search): Handle empty search queries

Previously, empty search would return all results.
Now returns friendly message: "Enter a search term"

Fixes #234
```

### docs

```
docs: Update README with new features

- Add installation section
- Document configuration options
- Add troubleshooting guide
```

### refactor

```
refactor(auth): Extract token validation

- Moved validation logic to TokenValidator class
- Added configurable expiration check
- Improved error messages

Part of #345
```

### perf

```
perf(db): Add index on user email column

Query time improved:
- Before: 250ms average
- After: 15ms average

Analyzed with EXPLAIN ANALYZE
```

### test

```
test(api): Add tests for user endpoint

- Happy path tests
- Validation error cases
- Authentication required tests
- Rate limiting tests
```

## Checklist

### Before Committing

- [ ] Type is correct
- [ ] Scope is appropriate
- [ ] Description is clear
- [ ] Message is under 72 chars
- [ ] No period at end
- [ ] Imperative mood used
- [ ] Body explains why (if added)
- [ ] Breaking changes documented
- [ ] Issues referenced

## Anti-Patterns

### 1. WIP Commits

Work in progress commits:
- Signals incomplete work
- Polls history
- Confuses reviewers

**Solution**: Use branches with WIP prefix, squash before merge.

### 2. Copy-Paste Commit Messages

Duplicating other messages:
- Doesn't describe your change
- Misleading in history

**Solution**: Write fresh, specific messages.

### 3. Blame Game

Trying to hide changes:
- Generic messages
- "Update file"

**Solution**: Be honest and specific.

### 4. Feature Commits

Bundling multiple features:
- Can't revert one feature
- Hard to cherry-pick

**Solution**: One commit per logical change.

### 5. Auto-Generated Only

Relying on auto-generated messages:
- Doesn't explain context
- Missing "why"

**Solution**: Enhance auto-generated with meaningful details.

## Future Improvements

- Set up commit message templates
- Create tooling for conventional commits
- Develop commit message generators
- Build automated changelog generation
- Create commit message API for automation

## Related Standards

- [09-Git-Workflow](09-Git-Workflow.md) — Git operations
- [10-Branching-Strategy](10-Branching-Strategy.md) — Branch organization
- [12-Pull-Request-Standards](12-Pull-Request-Standards.md) — PR workflow
