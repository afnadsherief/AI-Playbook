---
Status: Active
Version: 1.1
Maturity: Production
Owner: Engineering Team
Category: Knowledge Foundation
Last Reviewed: 2026-07-24
Next Review: 2026-10-24
---

# AI-Playbook Index

Primary navigation and knowledge map for the AI-Playbook repository.

## Overview

AI-Playbook is the canonical knowledge and standards repository for building reliable AI systems. It serves as the durable reference layer for engineering practices, prompt design, context engineering, orchestration patterns, and organizational governance.

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

## Current Direction

The repository is being organized into durable volumes so the knowledge base can scale without fragmenting into unrelated folders.

## Planned Volumes

- Volume I — Engineering
- Volume II — Context Engineering
- Volume III — AI Architecture
- Volume IV — Orchestration
- Volume V — Operations & Governance

## Governance

Before any new domain is added, the index, glossary, and terminology documents must be updated together so the repository stays internally consistent.

## Related Documents

- [GLOSSARY](./GLOSSARY.md)
- [TERMINOLOGY](./TERMINOLOGY.md)
- [EVOLUTION](./EVOLUTION.md)
- [COGNITIVE](./COGNITIVE.md)
- [RFC README](./RFC/README.md)

## Related RFCs

- [0001: Prompt Contracts](./RFC/0001-Prompt-Contracts.md)
- [0002: Prompt Observability](./RFC/0002-Prompt-Observability.md)
- [0008: Engineering Dependency Model](./RFC/0008-Engineering-Dependency-Model.md)

## Future Evolution

This index will expand as:
- New volumes are published
- Context and memory systems are formalized
- More orchestration patterns are standardized
- Automated maturity tracking is added

_Last Updated: 2026-07-24_
