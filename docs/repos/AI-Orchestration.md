# AI-Orchestration

## Location
- **Local (canonical):** `C:\Users\Afnad Sherief\AI\Core\orchestration\AI-Orchestration`
- **GitHub:** https://github.com/afnadsherief/AI-Orchestration

## Purpose
Meta-orchestration layer providing execution contracts, selector framework, and governance for the AI-Company ecosystem. Defines HOW systems should execute, not the execution itself.

## System Role
Control

## Architecture Summary
Spec-driven architecture with implemented foundation:
- **core/contracts/** — TypeScript interfaces + Zod schemas (execution-plan, intent, artifact-metadata, etc.)
- **core/shared/** — logging, errors, validators, types, constants
- **core/conductor/** — README stub (planned)
- **core/execution-engine/** — README stub (planned)
- **core/selectors/** — README stubs (planned: agent, knowledge, model, repository, tool, workflow)
- **docs/specifications/** — 22 comprehensive specification documents
- **docs/architecture/** — ADRs, matrices, diagrams

## Key Modules
- `core/contracts/` — approved-execution-plan, artifact-metadata, context-package, execution-plan, execution-result, intent, normalized-request, runtime-session, validated-response
- `core/shared/` — constants, errors, logging, types, utils, validators
- `docs/specifications/` — 22 specs (agent-selector through writing-standard)
- `docs/architecture/` — ADRs, decision-log, dependency-matrix, etc.

## Dependencies
- design-intelligence (runtime that orchestration controls)
- AI-Playbook (knowledge layer)

## Capabilities (tags)
orchestration, contracts, governance, specifications, selectors, execution-planning

## Maturity Level
L2 Active (foundation implemented, engine stubs)

## Related Systems
- design-intelligence (runtime)
- AI-Playbook (knowledge)

## Risks
- **CRITICAL: 12 unpushed local commits** — local has 82 TypeScript files not on GitHub
- Specs are hypothetical — conductor/execution-engine/selectors not implemented
- Orchestration module names don't map to design-intelligence actual modules

## Notes
Local version is significantly more advanced than GitHub. Must push local commits to prevent data loss. The control layer should either implement the specs or align them with design-intelligence as the actual runtime.
