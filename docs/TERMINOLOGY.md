---
Status: Active
Version: 1.1
Maturity: Production
Owner: Engineering Team
Category: Knowledge Foundation
Last Reviewed: 2026-07-24
Next Review: 2026-10-24
---

# Terminology Standards

Language and naming conventions for AI-Playbook documentation.

## Purpose

This document establishes consistent language across the repository, ensuring clarity, professionalism, and vendor-neutrality.

## Language Principles

### 1. Be Precise

Use exact, unambiguous language.

| Preferred | Avoid |
|-----------|-------|
| "The system validates input" | "The system checks input" |
| "The component returns output" | "The component gives back" |
| "Achieves 95% accuracy" | "Gets 95% right" |

### 2. Be Concise

Remove unnecessary words.

| Preferred | Avoid |
|-----------|-------|
| "Implement validation" | "Proceed to implement validation" |
| "Review required" | "It is required that review be performed" |
| "Use X for Y" | "In order to accomplish Y, one should use X" |

### 3. Be Direct

State requirements clearly.

| Preferred | Avoid |
|-----------|-------|
| "Must validate input" | "Input validation is recommended" |
| "Do not log credentials" | "Please avoid logging credentials when possible" |
| "Required fields marked with *" | "Fields that are required are marked with an asterisk" |

### 4. Be Neutral

Avoid vendor-specific or marketing language.

| Preferred | Avoid |
|-----------|-------|
| "AI model" | "AI", "the AI", "AI assistant" |
| "Token" | "Token" with vendor-specific pricing |
| "System prompt" | "Magic prompt", "ultimate instruction" |

## Naming Conventions

### Engineering Domains

| Domain | Naming | Example |
|--------|--------|---------|
| Domain folder | kebab-case | `prompt-engineering` |
| Domain name | Title Case | "Prompt Engineering" |
| Domain adjective | hyphenated | "prompt-engineering-specific" |

### Repository Names

| Element | Convention | Example |
|---------|------------|---------|
| Root folders | kebab-case | `docs/`, `specs/` |
| Subfolders | kebab-case | `prompt-engineering/` |
| Documentation | kebab-case | `api-reference.md` |

### Document Titles

| Type | Convention | Example |
|------|------------|---------|
| Standard | Title Case | "Engineering Standards" |
| RFC | "RFC NNNN: Title" | "RFC 0001: Prompt Contracts" |
| ADR | "ADR NNNN: Title" | "ADR 0012: Versioning Strategy" |
| Template | Title Case | "Architecture Review Template" |

### RFC Naming

Format: `NNNN-title.md`

| Element | Convention |
|---------|------------|
| Number | 4 digits, zero-padded |
| Title | kebab-case |
| Separator | hyphen |

Examples:
- `0001-prompt-contracts.md`
- `0002-prompt-observability.md`
- `0015-error-handling-strategy.md`

### ADR Naming

Format: `NNNN-title.md`

Same conventions as RFC naming.

### Specification Naming

| Type | Convention | Example |
|------|------------|---------|
| Schema | kebab-case | `prompt-schema.yaml` |
| Config | kebab-case | `model-config.yaml` |
| API Spec | kebab-case | `prompt-registry.yaml` |

### Folder Naming

| Type | Convention | Example |
|------|------------|---------|
| Domain folders | kebab-case | `prompt-engineering/` |
| Component folders | kebab-case | `order-processor/` |
| Private folders | prefixed underscore | `_schemas/` |

### Version Terminology

| Term | Definition |
|------|------------|
| Major version | Breaking changes |
| Minor version | New features, backward compatible |
| Patch version | Bug fixes |
| Pre-release | alpha, beta, rc |

## Governance Terminology

### Document States

| State | Meaning |
|-------|---------|
| Draft | Work in progress, not ready for review |
| Active | Open for use and review |
| Deprecated | Will be removed, do not use for new work |
| Archived | Retained for reference, no longer maintained |

### Maturity Levels

| Level | Abbr | Meaning |
|-------|------|---------|
| Draft | D | Initial work, unstable |
| Experimental | X | Proposed, unproven |
| Emerging | E | Approved, under validation |
| Stable | S | Proven through use |
| Production | P | Fully adopted |
| Institutional | I | Core practice |
| Deprecated | X | Superseded |
| Archived | A | Retained for reference |

### Lifecycle Stages

| Stage | Definition |
|-------|------------|
| Idea | Initial concept identified |
| Draft | Work in progress |
| RFC | Formal proposal submitted |
| Review | Community feedback period |
| Prototype | Implementation for validation |
| Approval | Decision gate |
| ADR | Decision documented |
| Standard | Published as standard |
| Production | In operational use |
| Institutional | Organizational norm |
| Deprecated | Being phased out |
| Archived | Retained for reference |

## Usage Notes

### Prompt vs. Instruction

| Term | Usage |
|------|-------|
| Prompt | Structured input to AI system |
| Instruction | Directive within a prompt |

### Context vs. Memory

| Term | Usage |
|------|-------|
| Context | Information provided at request time |
| Memory | Information retained across requests |

### Tool vs. Function

| Term | Usage |
|------|-------|
| Tool | Capability invoked by agent |
| Function | Mathematical or programmatic function |

### Test vs. Evaluate

| Term | Usage |
|------|-------|
| Test | Verify specific behavior |
| Evaluate | Assess overall quality or performance |

## Related Documents

- [INDEX](./INDEX.md)
- [GLOSSARY](./GLOSSARY.md)
- [EVOLUTION](./EVOLUTION.md)
- [COGNITIVE](./COGNITIVE.md)

## Related RFCs

- [0001: Prompt Contracts](./RFC/0001-Prompt-Contracts.md)
- [0002: Prompt Observability](./RFC/0002-Prompt-Observability.md)
- [0008: Engineering Dependency Model](./RFC/0008-Engineering-Dependency-Model.md)

## Related Templates

- [Architecture Review](./templates/Architecture-Review-Template.md)

_Last Updated: 2026-07-24_
