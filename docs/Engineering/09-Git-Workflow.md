---
Status: Active
Version: 1.0
Owner: Engineering Team
Category: Version Control
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Git Workflow

Standards for using Git effectively in team environments.

## Purpose

Establish practices that:
- Enable parallel work without conflict
- Maintain clean, readable history
- Support efficient code review
- Enable safe deployments

## Scope

Applies to:
- All Git operations
- All team members
- All repositories
- All branches

## Standards

### 1. Core Principles

#### Small, Frequent Commits

Break work into logical units:

```
# Good: Focused commits
abc1234 Add email validation to user registration
def5678 Update welcome email template
ghi9012 Add integration test for auth flow

# Bad: Monolithic commits
jkl3456 Lots of changes - auth, UI, tests, docs
```

#### Descriptive Messages

Every commit message should:
- Complete the sentence: "This commit will..."
- Be concise (under 72 characters)
- Explain *why*, not just *what*

#### Atomic Changes

Each commit should:
- Contain one logical change
- Be self-contained
- Be revertible independently

### 2. Repository Hygiene

#### Keep Main Clean

```
main: Always deployable, always safe
```

- Never commit directly to main
- Protect with branch rules
- Require PR reviews
- Fast-forward merges only

#### Clean Working State

Before switching branches:

```bash
# Option 1: Commit changes
git add .
git commit -m "WIP: in-progress work"
git checkout main
git pull
git checkout feature-branch
git rebase main

# Option 2: Stash changes
git stash
git checkout main
git pull
git checkout feature-branch
git stash pop
```

### 3. Workflow Patterns

#### Feature Branch Workflow

```
1. Create branch from main
   git checkout main
   git pull
   git checkout -b feature/add-user-avatars

2. Make commits
   git add .
   git commit -m "feat(ui): Add avatar upload component"
   git commit -m "feat(api): Add avatar storage endpoint"

3. Keep updated with main
   git fetch origin
   git rebase origin/main

4. Push and create PR
   git push -u origin feature/add-user-avatars

5. After review: squash if needed
   git rebase -i origin/main
```

#### Release Workflow

```
1. Prepare release branch
   git checkout main
   git pull
   git checkout -b release/v1.2.0

2. Make release-specific changes
   # Update version, changelog, etc.

3. Tag and merge
   git tag v1.2.0
   git checkout main
   git merge release/v1.2.0 --no-ff
   git push origin main --tags

4. Delete release branch
   git branch -d release/v1.2.0
```

#### Hotfix Workflow

```
1. Create hotfix from tag
   git checkout v1.1.0
   git checkout -b hotfix/critical-security-fix

2. Fix and commit
   git add .
   git commit -m "fix(security): Patch CVE-XXXX-XXXX"

3. Merge to main
   git checkout main
   git merge hotfix/critical-security-fix --no-ff
   git tag v1.1.1

4. Merge to release branches if needed
   git checkout v1.0-maintenance
   git merge hotfix/critical-security-fix

5. Delete hotfix branch
   git branch -d hotfix/critical-security-fix
```

### 4. Handling Conflicts

#### Rebase Conflicts

```bash
# Start rebase
git rebase origin/main

# Conflicts may occur. For each file:
# 1. Edit to resolve conflict
# 2. git add <file>
# 3. Continue rebase
git add conflicted-file.py
git rebase --continue

# If you want to abort:
git rebase --abort
```

#### Merge Conflicts

```bash
# Merge main into your branch
git merge main

# Resolve conflicts in editor
# Then commit merge:
git add .
git commit -m "merge: Resolve conflicts with main"
```

### 5. Collaboration Rules

#### Pulling Changes

```bash
# Prefer rebasing on main
git fetch origin
git rebase origin/main

# Avoid: git pull (creates merge commits)
```

#### Pushing Changes

```bash
# Use --force-with-lease for safety
# Only on your own branches!
git push --force-with-lease origin feature/my-branch

# Never force push to main
```

## Examples

### Good: Well-Structured History

```
* abc123f (HEAD -> main) Merge pull request #42
|\  
| * def456e Add user profile pictures
| * 789abcd Fix avatar upload size limit
| * 345efgh Add avatar upload component
|/
* abc111a Previous commit
```

### Bad: Messy History

```
* Merge branch 'feature' into main
|\  
| * WIP
| * asdf123 stuff
| * Merge branch 'origin/main'
| |\  
| | * temp
| | * more temp
| | * Revert "Revert "changes""
| | * Revert "changes"
| | * changes
* * * lots of merge commits
```

## Checklist

### Pre-Commit

- [ ] Changes are atomic
- [ ] Message follows convention
- [ ] No secrets included
- [ ] Tests pass locally

### Pre-Merge

- [ ] Branch is rebased on main
- [ ] Conflicts resolved
- [ ] CI passing
- [ ] Review approved

### Post-Merge

- [ ] Branch deleted
- [ ] Any tags created
- [ ] Deployed if applicable

## Anti-Patterns

### 1. Large Commits

Everything in one commit:
- Can't revert partial changes
- Hard to review
- Difficult to bisect

**Solution**: Commit logically as you work.

### 2. Force Pushes to Shared

Overwriting shared history:
- Breaks teammates' work
- Loses commits
- Causes chaos

**Solution**: Never force push to shared branches.

### 3. Detached HEAD

Working in detached HEAD state:
- Changes not saved to branch
- Easy to lose work

**Solution**: Always work on a branch.

### 4. Merge Commits Everywhere

Overusing git merge:
- Cluttered history
- Hard to follow changes

**Solution**: Prefer rebase for linear history.

### 5. Committing Generated Files

Binary and generated files:
- Bloat repository
- Cause merge conflicts

**Solution**: Add to .gitignore; regenerate.

## Future Improvements

- Create Git aliases for common operations
- Set up commit message linting
- Implement history rewriting policies
- Build automation for release tagging
- Develop Git training materials

## Related Standards

- [10-Branching-Strategy](10-Branching-Strategy.md) — Branch organization
- [11-Commit-Convention](11-Commit-Convention.md) — Commit message format
- [12-Pull-Request-Standards](12-Pull-Request-Standards.md) — PR workflow
