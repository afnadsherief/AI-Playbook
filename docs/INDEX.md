---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Knowledge Foundation
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# AI-Playbook Index

Primary navigation and knowledge map for the AI-Playbook repository.

## Overview

AI-Playbook is a comprehensive engineering knowledge base for building reliable AI systems. This index provides navigation across all documentation domains and illustrates relationships between components.

---

## Repository Structure

```
AI-Playbook/
├── docs/                    # Human-readable documentation
│   ├── Engineering/         # Engineering standards
│   ├── Prompt-Engineering/  # Prompt engineering framework
│   ├── RFC/                 # Requests for Comments
│   └── templates/           # Document templates
├── specs/                   # Machine-readable specifications
├── adr/                     # Architecture Decision Records
├── benchmarks/              # Performance benchmarks
├── projects/                # Project documentation
├── knowledge/               # Knowledge base
├── security/                # Security guidelines
├── privacy/                 # Privacy guidelines
├── scripts/                 # Utility scripts
└── .github/                 # GitHub workflows
```

---

## Engineering Domains

### Core Domains

| Domain | Purpose | Status |
|--------|---------|--------|
| [Engineering](./Engineering/) | Foundational engineering standards | Production |
| [Prompt Engineering](./Prompt-Engineering/) | Systematic prompt development | Production |

### Supporting Domains

| Domain | Purpose | Status |
|--------|---------|--------|
| Security | Security guidelines and practices | Planned |
| Privacy | Privacy compliance guidelines | Planned |
| Benchmarks | Performance measurement standards | Planned |
| Projects | Project-specific documentation | Planned |
| Knowledge | General AI/ML knowledge base | Planned |

---

## Standards

### Engineering Standards

| # | Document | Description | Maturity |
|---|----------|-------------|----------|
| 01 | [Engineering Standards](./Engineering/01-Engineering-Standards.md) | Foundational principles | Production |
| 02 | [Repository Standards](./Engineering/02-Repository-Standards.md) | Repository organization | Production |
| 03 | [Architecture Standards](./Engineering/03-Architecture-Standards.md) | System design principles | Production |
| 04 | [Coding Standards](./Engineering/04-Coding-Standards.md) | Code quality guidelines | Production |
| 05 | [Documentation Standards](./Engineering/05-Documentation-Standards.md) | Documentation practices | Production |
| 06 | [Review Standards](./Engineering/06-Review-Standards.md) | Code review practices | Production |
| 07 | [Definition of Done](./Engineering/07-Definition-of-Done.md) | Completion criteria | Production |
| 08 | [Milestone Framework](./Engineering/08-Milestone-Framework.md) | Planning methodology | Production |
| 09 | [Git Workflow](./Engineering/09-Git-Workflow.md) | Version control practices | Production |
| 10 | [Branching Strategy](./Engineering/10-Branching-Strategy.md) | Branch management | Production |
| 11 | [Commit Convention](./Engineering/11-Commit-Convention.md) | Commit message format | Production |
| 12 | [Pull Request Standards](./Engineering/12-Pull-Request-Standards.md) | PR workflow | Production |

### Prompt Engineering Standards

| # | Document | Description | Maturity |
|---|----------|-------------|----------|
| 01 | [Overview](./Prompt-Engineering/01-Prompt-Engineering-Overview.md) | Framework introduction | Production |
| 02 | [Architecture](./Prompt-Engineering/02-Prompt-Architecture.md) | System design | Production |
| 03 | [Components](./Prompt-Engineering/03-Prompt-Components.md) | Prompt structure | Production |
| 04 | [Lifecycle](./Prompt-Engineering/04-Prompt-Lifecycle.md) | Lifecycle stages | Production |
| 05 | [Versioning](./Prompt-Engineering/05-Prompt-Versioning.md) | Change management | Production |
| 06 | [Review](./Prompt-Engineering/06-Prompt-Review.md) | Quality assurance | Production |
| 07 | [Evaluation](./Prompt-Engineering/07-Prompt-Evaluation.md) | Assessment framework | Production |
| 08 | [Testing](./Prompt-Engineering/08-Prompt-Testing.md) | Testing methodology | Production |
| 09 | [Benchmarking](./Prompt-Engineering/09-Prompt-Benchmarking.md) | Performance measurement | Production |
| 10 | [Security](./Prompt-Engineering/10-Prompt-Security.md) | Security considerations | Production |
| 11 | [Anti-Patterns](./Prompt-Engineering/11-Prompt-Anti-Patterns.md) | Common mistakes | Production |
| 12 | [Optimization](./Prompt-Engineering/12-Prompt-Optimization.md) | Performance tuning | Production |
| 13 | [Documentation](./Prompt-Engineering/13-Prompt-Documentation.md) | Documentation standards | Production |

---

## RFCs

Requests for Comments — proposals for new standards and architectural changes.

| RFC | Title | Maturity | Status |
|-----|-------|----------|--------|
| 0001 | [Prompt Contracts](./RFC/0001-Prompt-Contracts.md) | Experimental | Open |
| 0002 | [Prompt Observability](./RFC/0002-Prompt-Observability.md) | Experimental | Open |

**Lifecycle**: Idea → Draft → RFC → Review → Prototype → Approval → ADR → Standard → Production → Institutional → Deprecated → Archived

See [RFC README](./RFC/README.md) for process details.

---

## ADRs

Architecture Decision Records — documented decisions with rationale.

**Location**: `./adr/`

See [ADR Index](./adr/README.md) for full list.

---

## Templates

Reusable document templates for consistent documentation.

| Template | Purpose |
|----------|---------|
| [Architecture Review](./templates/Architecture-Review-Template.md) | Architecture review documentation |
| [RFC Template](./RFC/0000-rfc-template.md) | New RFC proposals |

---

## Specifications

Machine-readable specifications for tooling and automation.

| Section | Purpose |
|---------|---------|
| [Specs README](../specs/README.md) | Specifications overview |
| [Prompts](../specs/prompts/) | Prompt specifications (planned) |
| [API](../specs/api/) | API specifications (planned) |
| [Config](../specs/config/) | Configuration schemas (planned) |

---

## Benchmarks

Performance benchmarks and measurement standards.

**Location**: `./benchmarks/`

**Status**: Planned

---

## Projects

Project-specific documentation and artifacts.

**Location**: `./projects/`

**Status**: Planned

---

## Knowledge Map

Visual representation of documentation relationships:

```
                    ┌─────────────────────────────────────────────────┐
                    │                  AI-Playbook                      │
                    └─────────────────────────────────────────────────┘
                                        │
        ┌───────────────────────────────┼───────────────────────────────┐
        │                               │                               │
        ▼                               ▼                               ▼
┌───────────────┐              ┌───────────────┐              ┌───────────────┐
│  Engineering  │              │    RFCs       │              │     ADRs      │
│   Standards   │◄────────────►│  Proposals    │──────►──────►│  Decisions    │
└───────────────┘              └───────────────┘              └───────────────┘
        │                               │
        │                               ▼
        │                       ┌───────────────┐
        │                       │   Standards   │
        │                       │  (Adopted)    │
        │                       └───────────────┘
        │                               │
        ▼                               ▼
┌───────────────┐              ┌───────────────┐
│  Templates    │              │ Specifications│
│   (Guides)    │              │   (Machine)   │
└───────────────┘              └───────────────┘
```

### Domain Relationships

```
Engineering Standards
        │
        ├──► Prompt Engineering ◄───► RFCs
        │         │                    │
        │         ▼                    ▼
        │   Specifications       ADRs
        │         │
        │         ▼
        └──► Templates
                  │
                  ▼
            Benchmarks
```

### RFC Lifecycle Flow

```
Idea → Draft → RFC → Review → Prototype → Approval → ADR → Standard → Production → Institutional → Deprecated → Archived
```

---

## Maturity Dashboard

*Maturity overview across all standards (placeholder)*

| Domain | Documents | Production | Stable | Emerging | Experimental |
|--------|-----------|------------|--------|----------|--------------|
| Engineering | 12 | 12 | 0 | 0 | 0 |
| Prompt Engineering | 13 | 13 | 0 | 0 | 0 |
| RFCs | 2 | 0 | 0 | 0 | 2 |

*Implementation pending: Automated maturity tracking dashboard*

---

## Review Dashboard

*Document review status overview (placeholder)*

| Category | Due for Review | Overdue | Recently Updated |
|----------|---------------|---------|------------------|
| Engineering | 0 | 0 | — |
| Prompt Engineering | 0 | 0 | — |
| RFCs | 0 | 0 | — |

*Implementation pending: Automated review tracking dashboard*

---

## Recently Added

| Date | Document | Change |
|------|----------|--------|
| 2024-01-15 | Sprint 2.5 | Architecture Governance Framework |
| 2024-01-15 | Sprint 2 | Prompt Engineering Framework |
| 2024-01-15 | Sprint 1 | Engineering Standards |

*Auto-updated on each sprint merge*

---

## Quick Links

- [Engineering Standards README](./Engineering/README.md)
- [Prompt Engineering README](./Prompt-Engineering/README.md)
- [RFC Process](./RFC/README.md)
- [ADR Index](./adr/README.md)
- [Templates](./templates/)
- [Specifications](../specs/README.md)

---

## Related Documents

| Document | Relationship |
|----------|--------------|
| [GLOSSARY](./GLOSSARY.md) | Term definitions |
| [TERMINOLOGY](./TERMINOLOGY.md) | Language standards |
| [EVOLUTION](./EVOLUTION.md) | Volume roadmap |
| [COGNITIVE](./COGNITIVE.md) | Cognitive architecture |
| [RFC README](./RFC/README.md) | Governance lifecycle |

## Related RFCs

| RFC | Relationship |
|-----|--------------|
| [0001: Prompt Contracts](./RFC/0001-Prompt-Contracts.md) | Interface specifications |
| [0002: Prompt Observability](./RFC/0002-Prompt-Observability.md) | Runtime visibility |

## Related Specifications

| Specification | Relationship |
|--------------|--------------|
| [Specs README](../specs/README.md) | Machine-readable formats |

## Future Evolution

This index will expand as:
- New domains are added (Context, Memory, Reasoning, etc.)
- Volume II and beyond are published
- Dashboard placeholders are implemented

---

*Last Updated: 2024-01-15*
