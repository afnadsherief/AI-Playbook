# design-intelligence

## Location
- **Local:** `C:\AI\design-intelligence`
- **GitHub:** https://github.com/afnadsherief/design-intelligence

## Purpose
A-OS v3 — Autonomous Multi-Company AI Operating System. Deterministic execution engine that runs multiple companies simultaneously with safe code transformations, self-evolution, and Obsidian-based knowledge capture.

## System Role
L3 Runtime � **ACTIVE RUNTIME** (ADR-0002)

## Architecture Summary
Layered architecture with clear separation:
- **Evolution Layer** — multi-pass convergence engine (learn/adapt/memory/core)
- **Orchestration Layer** — deterministic multi-agent issue graph (aos/orchestrator)
- **Domain Agents** — 6 rule-based agents: SEO, CRM, SMM, security, conversion, pricing
- **Org Hierarchy** — 16-agent executive/core/domain structure (Merlin orchestrator)
- **Hermes Skills** — 5 deterministic pure skills (Ranker, PatternEye, Refactor, CopyForge, ComposeUI)
- **Docs Layer** — Obsidian execution logging
- **Company Layer** — multi-tenant isolation (S1-S3)

## Key Modules
- `system/evolution/` — learning, adaptation, memory, pipeline core
- `system/aos/` — orchestrator, adapters, patches, domain agents
- `system/org/` — registry, merlin
- `system/hermes/` — skills
- `system/docs/` — obsidian integration
- `system/company/` — company context, loader, configs
- `agents/design-qa/` — QA + fix agents
- `agents/generator/` — component generation
- `agents/ux-agent/` — UX optimization
- `agents/performance-agent/` — performance analysis

## Dependencies
- park-ui, ark, ui (shadcn) — design references
- Next.js, React, TypeScript, Tailwind CSS
- Hermes skills (internal)

## Capabilities (tags)
ai-agent, orchestration, evolution, deterministic, multi-tenant, code-transformation, seo, crm, smm, security, conversion, pricing, design-qa, self-evolving

## Maturity Level
L3 Production

## Related Systems
- AI-Orchestration (control layer specs)
- AI-Playbook (this knowledge base)
- ponytail (skill system)
- zeeddrops (target product)
- pranov / pranov-guardian (target products)

## Risks
- AI-Orchestration specs do not map 1:1 to actual modules
- 22 orchestration specs vs only contracts/utils implemented in control layer

## Notes
The production runtime for the entire A-OS ecosystem. All companies (zeeddrops, pranov, Gymverse) are intended to run through this engine.
