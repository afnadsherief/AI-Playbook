---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Prompt Engineering
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Prompt Versioning

Systematic change management for prompts.

## Purpose

Establish version control practices for prompts:

- Track changes systematically
- Enable rollback when needed
- Support collaboration
- Maintain history for auditing

## Scope

Applies to:

- All production prompts
- Prompt templates
- Prompt components
- Prompt configurations

## Core Principles

### 1. Semantic Versioning

Use semantic versioning for clear compatibility understanding:

```
Major.Minor.Patch
     │    │    └── Bug fixes
     │    └───────── New features (backward compatible)
     └────────────── Breaking changes
```

### 2. Immutable Versions

Once published, versions are immutable:

- Never modify released versions
- Fix issues in new versions
- Maintain changelog for each version
- Preserve historical releases

### 3. Clear Changelog

Document all changes between versions:

- Categorize changes (added, changed, deprecated, removed, fixed)
- Reference related issues or PRs
- Explain migration requirements
- Highlight breaking changes

### 4. Dependency Versioning

Pin dependencies to specific versions:

- Specify compatible version ranges
- Test with dependency versions
- Document known issues with versions
- Plan dependency updates

## Engineering Standards

### Version Number Format

```
{prompt-id}-v{major}.{minor}.{patch}

Example: PRMPT-ORDER-001-v2.1.0
```

### Version States

| State | Description | Can Rollback |
|-------|-------------|--------------|
| **Draft** | Work in progress | Yes |
| **Published** | Available for use | Via older version |
| **Deprecated** | Should not use | No |
| **Retired** | No longer available | No |

### Change Classification

| Type | Description | Version Impact |
|------|-------------|----------------|
| **Added** | New functionality | Minor |
| **Changed** | Modified behavior | Minor (or Major if breaking) |
| **Deprecated** | Will be removed | Patch |
| **Removed** | Deleted functionality | Major |
| **Fixed** | Bug correction | Patch |
| **Security** | Security improvement | Patch |

### Compatibility Levels

| Level | Description | Requirement |
|-------|-------------|-------------|
| **Full** | Drop-in replacement | No changes needed |
| **Partial** | Minor adjustments | Configuration update |
| **Breaking** | Significant changes | Code changes required |

## Workflow

### Versioning Workflow

```
Draft → Review → Publish → Monitor → (Iterate or Deprecate)
```

### Release Process

1. **Prepare Release**
   - Finalize changes
   - Update changelog
   - Update version number
   - Run final tests

2. **Review Release**
   - Code review
   - Security review
   - Performance review
   - Approval

3. **Publish Release**
   - Tag version
   - Update registry
   - Publish artifacts
   - Notify consumers

4. **Post-Release**
   - Monitor performance
   - Collect feedback
   - Document issues
   - Plan next version

### Rollback Process

1. **Detect Issue**
   - Performance degradation
   - Quality drop
   - Error increase

2. **Assess Scope**
   - Determine affected versions
   - Identify root cause
   - Evaluate rollback risk

3. **Execute Rollback**
   - Switch to previous version
   - Validate functionality
   - Monitor closely

4. **Post-Rollback**
   - Investigate root cause
   - Plan fix
   - Notify stakeholders

## Examples

### Changelog Entry

```yaml
version: PRMPT-ORDER-001-v2.1.0
date: 2024-01-15
changes:
  added:
    - Support for multiple order formats
    - Confidence scores in extraction
  
  changed:
    - Improved handling of partial order information
      (breaking for systems relying on exact format)
  
  deprecated:
    - "order_number" field (use "order_id" instead)
      deprecated_in: v2.0.0
      will_remove: v3.0.0
  
  fixed:
    - Incorrect price calculation for bulk orders
    - Missing customer name extraction
  
  security:
    - Improved input sanitization

migration:
  required: false
  notes: "Systems using order_number should migrate to order_id"
```

### Version Registry Entry

```yaml
registry:
  prompt_id: PRMPT-ORDER-001
  name: Order Information Extractor
  
  versions:
    v1.0.0:
      state: retired
      released: 2024-01-01
      retired: 2024-03-01
      changelog: |
        Initial release
      
    v1.1.0:
      state: deprecated
      released: 2024-02-01
      deprecated: 2024-04-01
      changelog: |
        Added validation for order format
        Fixed null pointer in empty email handling
      
    v2.0.0:
      state: deprecated
      released: 2024-03-01
      changelog: |
        Added support for multiple items
        Breaking: Changed output structure
        See migration guide v2.0.0
      
    v2.1.0:
      state: published
      released: 2024-01-15
      current: true
      changelog: |
        Added confidence scores
        Improved partial order handling

  latest: v2.1.0
  recommended: v2.1.0
```

## Checklist

### Release Checklist

- [ ] Version number incremented correctly
- [ ] Changelog updated with all changes
- [ ] Migration guide prepared (if needed)
- [ ] All tests passing
- [ ] Code review approved
- [ ] Security review completed
- [ ] Performance validated
- [ ] Documentation updated
- [ ] Registry updated
- [ ] Stakeholders notified

### Deprecation Checklist

- [ ] Deprecation notice published
- [ ] Replacement version available
- [ ] Migration guide provided
- [ ] Timeline communicated
- [ ] Consumers notified
- [ ] Registry updated
- [ ] Monitoring enhanced

## Anti-Patterns

### 1. No Versioning

Treating prompts as static:

**Problem**: No history, no rollback, no collaboration.

**Solution**: Apply versioning from initial creation.

### 2. Inconsistent Versioning

Different versioning approaches:

**Problem**: Confusion, compatibility issues.

**Solution**: Standardize on semantic versioning.

### 3. Skipping Version Numbers

Jumping versions arbitrarily:

**Problem**: Breaks tooling and processes.

**Solution**: Follow sequential versioning.

### 4. No Changelog

Releasing without documentation:

**Problem**: Unknown changes, migration difficulty.

**Solution**: Require changelog for all releases.

## Related Documents

- [04-Prompt-Lifecycle](04-Prompt-Lifecycle.md) — Lifecycle stages
- [06-Prompt-Review](06-Prompt-Review.md) — Review process
- [07-Prompt-Evaluation](07-Prompt-Evaluation.md) — Quality assessment
- [08-Prompt-Testing](08-Prompt-Testing.md) — Testing methodology

## Future Evolution

- **v1.1**: Automated changelog generation
- **v1.2**: Version compatibility checking
- **v1.3**: Migration assistant tools
- **v2.0**: Intelligent deprecation warnings
