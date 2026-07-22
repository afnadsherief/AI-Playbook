---
Status: Active
Version: 1.0
Maturity: Production
Owner: Engineering Team
Category: Knowledge Foundation
Last Reviewed: 2024-01-15
Next Review: 2024-07-15
---

# Repository Evolution

How AI-Playbook grows from Sprint 0 to production-ready knowledge base.

---

## Overview

AI-Playbook uses two parallel organization systems:

| System | Organization | Contents |
|--------|--------------|----------|
| **Sprints** | Time-based | Implementation work (branches, commits) |
| **Volumes** | Content-based | Published documentation (tags, releases) |

Understanding the relationship between these systems is essential for navigation.

---

## Sprints vs. Volumes

### Sprints (Implementation)

Sprints are time-boxed development iterations that create documentation incrementally.

```
Sprint 0: Bootstrap
    ↓
Sprint 1: Engineering Standards
    ↓
Sprint 2: Prompt Engineering
    ↓
Sprint 2.5: Architecture Governance
    ↓
Sprint 2.6: Knowledge Foundation
    ↓
Sprint 3: Context Engineering
    ↓
...
```

### Volumes (Publication)

Volumes are logical groupings of related standards, organized by engineering discipline.

```
Volume I: Engineering Foundations
    ↓
Volume II: Cognitive Engineering
    ↓
Volume III: Execution Engineering
    ↓
Volume IV: Trust Engineering
    ↓
Volume V: AI Factory
```

---

## Relationship Diagram

```
Implementation Pipeline
═══════════════════════════════════════════════════════════════
                    │
    ┌───────────────┼───────────────┐
    │               │               │
    ▼               ▼               ▼
┌─────────┐   ┌─────────┐   ┌─────────┐
│ Sprints │   │ Volumes │   │ Releases│
└─────────┘   └─────────┘   └─────────┘
    │               │               │
    │               │               │
    ▼               ▼               ▼
┌─────────┐   ┌─────────┐   ┌─────────┐
│ Work in │   │ Published│   │  Tags   │
│ Progress│   │ Content │   │  v0.x.x │
└─────────┘   └─────────┘   └─────────┘

Flow:
Sprint → Commit → Review → Merge → Volume → Release → Tag
```

---

## Volume Structure

### Volume I: Engineering Foundations

**Status**: In Progress (v0.4.0)

The foundational layer that all other volumes depend upon.

| Sprint | Contents |
|--------|----------|
| Sprint 0 | Repository bootstrap, folder structure, README |
| Sprint 1 | Engineering Standards (12 documents) |
| Sprint 2 | Prompt Engineering (13 documents) |
| Sprint 2.5 | Architecture Governance (RFCs, maturity) |
| Sprint 2.6 | Knowledge Foundation (index, glossary, terminology) |

**Planned additions**: ADR expansion, benchmark templates

---

### Volume II: Cognitive Engineering

**Status**: Planned

Systems that process and generate understanding.

| Domain | Description |
|--------|-------------|
| Context Engineering | Information delivery to AI systems |
| Memory Engineering | Information retention across sessions |
| Reasoning Engineering | Chain-of-thought and logic |
| Decision Engineering | Choice and action selection |
| Planning Engineering | Goal decomposition and sequencing |

**Dependencies**: Requires Volume I

---

### Volume III: Execution Engineering

**Status**: Planned

Systems that take action in the world.

| Domain | Description |
|--------|-------------|
| Workflow Engineering | Multi-step process orchestration |
| Tool Engineering | Capability definition and invocation |
| Agent Engineering | Autonomous action coordination |

**Dependencies**: Requires Volumes I and II

---

### Volume IV: Trust Engineering

**Status**: Planned

Systems that ensure quality and safety.

| Domain | Description |
|--------|-------------|
| Evaluation | Output quality assessment |
| Benchmarking | Standardized performance measurement |
| Security | Adversarial robustness |
| Privacy | Data protection and compliance |
| Governance | Policy enforcement and audit |

**Dependencies**: Requires all preceding volumes

---

### Volume V: AI Factory

**Status**: Planned

Production-grade implementation systems.

| Component | Description |
|-----------|-------------|
| Specifications | Machine-readable definitions |
| Prompt Compiler | Prompt versioning and deployment |
| Context Compiler | Context assembly and optimization |
| Memory Compiler | Memory consolidation and retrieval |
| Reasoning Engine | Logical inference systems |
| Decision Engine | Choice-making systems |
| Planning Engine | Goal-planning systems |
| Workflow Runtime | Process execution environment |
| Agent Runtime | Autonomous execution environment |
| Tool Registry | Capability catalog |
| Evaluation Engine | Automated quality assessment |
| Governance Engine | Policy enforcement engine |

**Dependencies**: Requires all preceding volumes

---

## Directory Naming Convention

All engineering domains follow a canonical directory naming pattern.

### Standard Format

```
docs/<Domain>-Engineering/
```

Examples:
- `docs/Context-Engineering/`
- `docs/Memory-Engineering/`
- `docs/Reasoning-Engineering/`
- `docs/Workflow-Engineering/`
- `docs/Agent-Engineering/`

### Existing Canonical Directories

| Directory | Description | Volume |
|-----------|-------------|--------|
| `docs/Engineering/` | Engineering Standards | I |
| `docs/Prompt-Engineering/` | Prompt Engineering | I |

### Benefits

| Benefit | Description |
|---------|-------------|
| **Consistency** | Uniform pattern across all volumes |
| **Navigation** | Predictable location for domain content |
| **Discoverability** | Easy to find and explore domains |
| **Automation** | Compatible with build scripts and tooling |
| **AI Indexing** | Semantic search optimization |
| **Future-proof** | Pattern scales to any future domain |

### Governance

Per the **Domain Introduction Protocol** (see RFC README), every new engineering domain must:
1. Update `INDEX.md` with directory location
2. Update `TERMINOLOGY.md` with naming convention
3. Follow the `<Domain>-Engineering/` pattern

**Exception**: Only via ADR approval

### References

- [TERMINOLOGY.md](./TERMINOLOGY.md) — Full naming standards
- [INDEX.md](./INDEX.md) — Domain directory listings
- [RFC-0008](./RFC/0008-Engineering-Dependency-Model.md) — Engineering Dependency Model

---

## Volume Relationship Diagram

```
AI-Playbook Volume Architecture
═══════════════════════════════════════════════════════════════

Volume V: AI Factory
    │
    │  Requires
    ▼
Volume IV: Trust Engineering
    │
    │  Requires
    ▼
Volume III: Execution Engineering
    │
    │  Requires
    ▼
Volume II: Cognitive Engineering
    │
    │  Requires
    ▼
Volume I: Engineering Foundations
    │
    │  Built on
    ▼
    ┌─────────────────────────────────────────┐
    │  Sprint 0 → Sprint 1 → Sprint 2 → ... │
    └─────────────────────────────────────────┘
```

---

## From Standards to Implementation

```
┌─────────────┐
│   Volumes   │  ← Organized by discipline
└──────┬──────┘
       │ contains
       ▼
┌─────────────┐
│  Standards  │  ← Engineering guidelines
└──────┬──────┘
       │ specifies
       ▼
┌─────────────┐
│Specifications│  ← Machine-readable schemas
└──────┬──────┘
       │ implemented by
       ▼
┌─────────────┐
│   Sprints   │  ← Development iterations
└──────┬──────┘
       │ produces
       ▼
┌─────────────┐
│   Releases  │  ← Versioned snapshots
└─────────────┘
```

---

## Release Cadence

| Phase | Frequency | Contents |
|-------|----------|----------|
| **Major** (v1.0, v2.0) | Volume complete | Full discipline coverage |
| **Minor** (v0.3, v0.4) | Sprint merged | New domain added |
| **Patch** (v0.4.1) | Hotfix | Error corrections |

---

## Current Status

| Metric | Value |
|--------|-------|
| Current Version | v0.4.0 |
| Volume Progress | Volume I: ~90% |
| Sprints Completed | 0, 1, 2, 2.5, 2.6 |
| Sprints Planned | 3+ |
| Volumes Planned | 5 |

---

## Future Evolution

### Volume Completion Path

```
v0.4.0 (current)
    │
    ▼
v0.5.0: Sprint 3 (Context Engineering)
    │
    ▼
v0.6.0: Sprint 4 (Memory Engineering)
    │
    ▼
v0.7.0: Sprint 5 (Reasoning Engineering)
    │
    ▼
v0.8.0: Sprint 6 (Decision + Planning Engineering)
    │
    ▼
v0.9.0: Sprint 7 (Execution domains)
    │
    ▼
v1.0.0: Volume I Complete
```

### Governance Evolution

As volumes complete, governance will evolve:

| Phase | Governance Model |
|-------|-----------------|
| v0.x | Contributor-driven |
| v1.x | Committee-driven |
| v2.x | Standards-body |

---

## Future RFCs

RFC roadmap for Volume II and beyond:

| RFC | Title | Volume | Sprint |
|-----|-------|--------|--------|
| RFC 0003 | Context Engineering | II | 3 |
| RFC 0004 | Memory Engineering | II | 4 |
| RFC 0005 | Cognitive Stack Specification | II | 5 |
| RFC 0006 | Layer Integration Protocol | II | 5 |
| RFC 0007 | Agent Execution Model | III | 7 |
| RFC 0008 | Engineering Dependency Model | I | 2.7 (this sprint) |

---

## Related Documents

- [INDEX](./INDEX.md) — Repository navigation
- [GLOSSARY](./GLOSSARY.md) — Term definitions
- [RFC README](./RFC/README.md) — RFC lifecycle
- [Engineering Standards](../Engineering/) — Volume I content
- [Prompt Engineering](../Prompt-Engineering/) — Volume I content
- [Cognitive Architecture](./COGNITIVE.md) — Cognitive stack roadmap

---

*Last Updated: 2024-01-15*
