# Engineering Standards

Production-grade engineering standards that govern every repository.

## Overview

This section contains comprehensive standards for all aspects of engineering work, from coding practices to release management. Each document includes metadata for tracking and versioning.

## Documents

### Foundational Standards

| # | Document | Description |
|---|----------|-------------|
| 01 | [01-Engineering-Standards.md](01-Engineering-Standards.md) | Core engineering principles and quality standards |
| 07 | [07-Definition-of-Done.md](07-Definition-of-Done.md) | Criteria for completed work |

### Code & Documentation

| # | Document | Description |
|---|----------|-------------|
| 04 | [04-Coding-Standards.md](04-Coding-Standards.md) | Language-agnostic coding practices |
| 05 | [05-Documentation-Standards.md](05-Documentation-Standards.md) | Creating clear, maintainable documentation |
| 02 | [02-Repository-Standards.md](02-Repository-Standards.md) | Repository organization and configuration |
| 06 | [06-Review-Standards.md](06-Review-Standards.md) | Conducting effective reviews |

### Architecture & Design

| # | Document | Description |
|---|----------|-------------|
| 03 | [03-Architecture-Standards.md](03-Architecture-Standards.md) | System design principles |

### Project Management

| # | Document | Description |
|---|----------|-------------|
| 08 | [08-Milestone-Framework.md](08-Milestone-Framework.md) | Planning and tracking milestones |

### Version Control

| # | Document | Description |
|---|----------|-------------|
| 09 | [09-Git-Workflow.md](09-Git-Workflow.md) | Effective Git practices |
| 10 | [10-Branching-Strategy.md](10-Branching-Strategy.md) | Branch organization patterns |
| 11 | [11-Commit-Convention.md](11-Commit-Convention.md) | Writing clear commit messages |
| 12 | [12-Pull-Request-Standards.md](12-Pull-Request-Standards.md) | PR creation and review process |

## RFC Process

Propose new standards or significant changes through the [RFC process](../RFC/).

**Lifecycle**: RFC → Review → Accepted → ADR → Standard

## Quick Reference

### Commit Types

```
feat    - New feature
fix     - Bug fix
docs    - Documentation
style   - Formatting
refactor- Code restructure
perf    - Performance
test    - Tests
build   - Build system
ci      - CI/CD
chore   - Maintenance
```

### Branch Prefixes

```
feature/*   - New features
fix/*       - Bug fixes
hotfix/*    - Production emergencies
refactor/*  - Code improvements
docs/*      - Documentation
```

### PR Title Format

```
{type}({scope}): {description}

Example: feat(auth): Add OAuth2 Google login
```

## Related

- [RFC Index](../RFC/) — Requests for Comments
- [ADR Index](../../adr/) — Architecture Decision Records
- [Knowledge Base](../../knowledge/) — Patterns and best practices
- [Contributing Guide](../../CONTRIBUTING.md) — How to contribute to this playbook
