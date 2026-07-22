---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Version Control
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Branching Strategy

Standards for organizing work with Git branches.

## Purpose

Provide a consistent branching model that:
- Enables parallel development
- Protects stable code
- Simplifies releases
- Supports all workflows

## Scope

Applies to:
- All repositories
- All team members
- All deployment environments

## Branch Types

### 1. Protected Branches

These branches are never worked on directly:

| Branch | Purpose | Protection |
|--------|---------|------------|
| `main` | Production-ready code | Required reviews, required checks |
| `staging` | Pre-production testing | Required reviews, required checks |
| `develop` | Integration branch (if used) | Required reviews |

### 2. Long-Lived Branches

Persistent branches for coordination:

| Branch | Purpose | Lifetime |
|--------|---------|----------|
| `main` | Production releases | Permanent |
| `release/*` | Release preparation | Until release complete |
| `maintenance/*` | Supporting old versions | Until EOL |

### 3. Short-Lived Branches

Feature and fix branches:

| Prefix | Purpose | Example |
|--------|---------|---------|
| `feature/*` | New features | `feature/user-authentication` |
| `fix/*` | Bug fixes | `fix/login-redirect-loop` |
| `hotfix/*` | Production emergencies | `hotfix/security-patch` |
| `refactor/*` | Code improvements | `refactor/user-service` |
| `docs/*` | Documentation | `docs/api-reference` |
| `experiment/*` | Exploratory work | `experiment/new-algorithm` |

## Branch Naming

### Conventions

```
{type}/{short-description}

Examples:
feature/user-registration
fix/checkout-validation-error
hotfix/critical-security-patch
refactor/payment-processing
```

### Naming Rules

- Use lowercase
- Use hyphens as separators
- Keep under 50 characters
- Include ticket number if applicable: `feature/PROJ-123/user-registration`

### Anti-Examples

```
# Bad: Too vague
feature/work
fix/bug

# Bad: Too long
feature/add-the-ability-to-export-user-data-to-csv-format-with-headers

# Bad: Uses underscores
feature/add_user_export

# Bad: Uses mixed case
Feature/UserRegistration
```

## Branch Lifecycle

```
                                                                                                                                                                                 
                        BRANCH LIFECYCLE                        
                                                                                                                                                                                 

                                                                                                                      
     create                        develop                         review     
                                                                                                                      
                                              
                                              
                                                                     
                                   revisions   
                                                                     
                                       
                                       
                                                                                                                      
     delete                         merge                          approve    
                                                                                                                      
```

### 1. Create

```bash
# From main, create feature branch
git checkout main
git pull
git checkout -b feature/user-avatars
```

### 2. Develop

```bash
# Make commits
git add .
git commit -m "feat(ui): Add avatar upload component"

# Keep updated
git fetch origin
git rebase origin/main
```

### 3. Review

```bash
# Push branch
git push -u origin feature/user-avatars

# Create PR via GitHub/GitLab
```

### 4. Merge

```bash
# After approval, merge via PR
# Squash if requested
# Delete branch after merge
```

## Branch Protection Rules

### Main Branch

```
Required settings:
    Require pull request reviews (1-2 approvers)
    Require status checks to pass
    Require branches to be up to date
    Restrict who can push
    Include administrators
    Do not allow force pushes
    Do not allow deletions
```

### Release Branches

```
Required settings:
    Require pull request reviews (1 approver)
    Require status checks to pass
    Prevent force pushes
    Allow deletions (after merge)
```

### Feature Branches

```
Settings:
    No restrictions (contributors)
    Delete after merge
```

## Release Branching

### Creating Release Branches

```bash
# When ready for release
git checkout main
git pull
git checkout -b release/v1.2.0

# Make release-specific changes
# Update version numbers
# Update changelog
# Create PR to main
```

### Maintenance Branches

```bash
# For supporting older versions
git checkout v1.0.0
git checkout -b maintenance/v1.0.x

# Apply security patches
# Tag new versions: v1.0.1, v1.0.2, etc.
```

## Examples

### Good: Clean Branch Structure

```
main
          feature/user-avatars (merged)
          feature/dark-mode (merged)
          feature/export-csv (in review)
          fix/typo-in-docs (merged)
          hotfix/security-patch (merged)
```

### Bad: Messy Branches

```
main
          Feature-User-Authentication
          bugfix
          fix_auth
          new_feature
          user_avatars_final
          user_avatars_final_v2
          user_avatars_final_v3_REALLY_FINAL
```

## Checklist

### Branch Creation

- [ ] Created from correct base
- [ ] Follows naming convention
- [ ] Has descriptive name
- [ ] Linked to issue/ticket

### Branch Maintenance

- [ ] Regularly rebased on main
- [ ] Commits are atomic
- [ ] Messages are clear

### Branch Completion

- [ ] All tests pass
- [ ] Review approved
- [ ] Merged correctly
- [ ] Branch deleted

## Anti-Patterns

### 1. Branch Proliferation

Too many active branches:
- Hard to track
- Merge conflicts
- Stale code

**Solution**: Keep branches short-lived; limit WIP.

### 2. Long-Lived Features

Features that take months:
- Huge merge conflicts
- Outdated code
- Scope creep

**Solution**: Use feature flags; ship incrementally.

### 3. Direct Main Commits

Bypassing review process:
- Quality issues
- Security risks
- Blame diffusion

**Solution**: Enforce branch protection; use pre-commit hooks.

### 4. Inconsistent Naming

Random branch names:
- Hard to search
- Unclear purpose
- Messy history

**Solution**: Enforce naming conventions.

### 5. Forgotten Branches

Unused branches left behind:
- Confusion
- Outdated code
- Zombie branches

**Solution**: Delete after merge; regular cleanup.

## Future Improvements

- Automate branch naming validation
- Create branch cleanup automation
- Set up branch age monitoring
- Develop branch analytics
- Create branch templates

## Related Standards

- [09-Git-Workflow](09-Git-Workflow.md) — Git operations
- [11-Commit-Convention](11-Commit-Convention.md) — Commit workflow
- [12-Pull-Request-Standards](12-Pull-Request-Standards.md) — PR lifecycle
