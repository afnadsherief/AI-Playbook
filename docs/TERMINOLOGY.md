# Terminology Standards

Language and naming conventions for AI-Playbook documentation.

## Purpose

This document establishes consistent language across the repository, ensuring clarity, professionalism, and vendor-neutrality.

---

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

---

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

---

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

---

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

---

## Examples

### Document Header

```markdown
---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Engineering Standards
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---
```

### RFC Header

```markdown
---
Status: RFC
Maturity: Experimental
Version: 1.0
Owner: Engineering Team
Category: Prompt Engineering
Created: 2024-01-15
Last Updated: 2024-01-15
RFC Number: 0001
---
```

### ADR Header

```markdown
---
status: accepted
date: 2024-01-15
authors:
  - name: Author Name
    email: author@company.com
deciders:
  - name: Decider Name
---
```

---

## Words to Avoid

### Marketing Language

| Avoid | Reason |
|-------|--------|
| Magic | Implies unexplainable |
| Ultimate | Marketing superlative |
| Super | Marketing superlative |
| Amazing | Marketing superlative |
| Revolutionary | Marketing superlative |
| Game-changer | Marketing cliché |

### Vague Terms

| Avoid | Use Instead |
|-------|-------------|
| Stuff | Specific term |
| Things | Specific term |
| Maybe | Specific assessment |
| Somehow | Specific method |
| Eventually | Specific timeline |

### Jargon

| Avoid | Use Instead |
|-------|-------------|
| Synergy | Collaboration |
| Leverage | Use |
| Circle back | Follow up |
| Deep dive | Detailed analysis |
| Low-hanging fruit | Easy wins |

---

## Case Conventions

| Convention | Usage | Example |
|------------|-------|---------|
| Title Case | Document titles, headings | "Engineering Standards" |
| Sentence case | Body text, descriptions | "the prompt validates input" |
| UPPER CASE | Acronyms, warnings | "DO NOT USE", "RFC" |
| kebab-case | File names, URLs | `engineering-standards.md` |
| camelCase | Code identifiers | `orderExtractor` |
| snake_case | Variable names | `order_id` |

---

## Document Structure Language

### Required Sections

Every standard document should include:

1. **Purpose** — Why this document exists
2. **Scope** — What it covers
3. **Core Principles** — Fundamental guidelines
4. **Standards** — Specific requirements
5. **Workflow** — Process documentation
6. **Examples** — Concrete illustrations
7. **Checklist** — Verification items
8. **Anti-Patterns** — Common mistakes
9. **Related Documents** — Cross-references
10. **Future Evolution** — Planned changes

### Metadata Header

Every document should have YAML frontmatter:

```yaml
---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Engineering Standards
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---
```

---

*Last Updated: 2024-01-15*
