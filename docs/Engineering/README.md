# Engineering Standards

Production-grade engineering standards that govern every repository.

## Overview

This section contains comprehensive standards for all aspects of engineering work, from coding practices to release management.

## Documents

### Foundational Standards

| Document | Description |
|----------|-------------|
| [Engineering-Standards.md](Engineering-Standards.md) | Core engineering principles and quality standards |
| [Definition-of-Done.md](Definition-of-Done.md) | Criteria for completed work |

### Code & Documentation

| Document | Description |
|----------|-------------|
| [Coding-Standards.md](Coding-Standards.md) | Language-agnostic coding practices |
| [Documentation-Standards.md](Documentation-Standards.md) | Creating clear, maintainable documentation |
| [Repository-Standards.md](Repository-Standards.md) | Repository organization and configuration |

### Architecture & Design

| Document | Description |
|----------|-------------|
| [Architecture-Standards.md](Architecture-Standards.md) | System design principles |
| [Review-Standards.md](Review-Standards.md) | Conducting effective reviews |

### Project Management

| Document | Description |
|----------|-------------|
| [Milestone-Framework.md](Milestone-Framework.md) | Planning and tracking milestones |

### Version Control

| Document | Description |
|----------|-------------|
| [Git-Workflow.md](Git-Workflow.md) | Effective Git practices |
| [Branching-Strategy.md](Branching-Strategy.md) | Branch organization patterns |
| [Commit-Convention.md](Commit-Convention.md) | Writing clear commit messages |
| [Pull-Request-Standards.md](Pull-Request-Standards.md) | PR creation and review process |

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

- [ADR Index](../../adr/) - Architecture Decision Records
- [Knowledge Base](../../knowledge/) - Patterns and best practices
- [Contributing Guide](../../CONTRIBUTING.md) - How to contribute to this playbook
