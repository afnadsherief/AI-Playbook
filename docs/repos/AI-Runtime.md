# AI-Runtime

## Location
- **Local:** `C:\AI\AI-Runtime`
- **GitHub:** ❌ Not on GitHub — not yet a git repository

## Purpose
Declares the **execution layer** boundary. Created to separate "doing" from "deciding" (AI-Orchestration) and "describing" (AI-Playbook). Currently a documented scaffold with no implementation.

## System Role
L3 Runtime � **abstraction layer, NOT ACTIVE** (ADR-0002)

## Architecture Summary
Standard three-layer directory scaffold with a specification README. No code. The README defines intake contracts (`ApprovedExecutionPlan`, `ContextPackage`, `RuntimeSession`), return contracts (`ExecutionResult`, `ArtifactMetadata`), and nine execution responsibilities.

Until populated, **`design-intelligence` remains the de-facto runtime.**

## Key Modules
- `docs/` — runtime specifications (empty)
- `src/` — execution implementation (empty)
- `configs/` — runtime configuration (empty)
- `registry/` — adapter/capability registry (empty)
- `README.md` — layer definition and responsibilities

## Dependencies
- AI-Orchestration (`core/contracts/` — consumes execution-plan and session contracts)

## Capabilities (tags)
- runtime
- execution
- orchestration

## Maturity Level
L0 Idea

## Related Systems
- AI-Orchestration (control layer, supplies plans)
- design-intelligence (current de-facto runtime)
- AI-Playbook (knowledge layer)

## Risks
- **Third competing definition of "runtime"** — alongside `AI-Orchestration/core/execution-engine/` (stub) and `design-intelligence/system/aos/` (working). Creating this scaffold makes the conflict visible; it does not resolve it.
- Not a git repository — unversioned.
- Risks becoming another empty skeleton like `AI-Workspace` if not populated or retired.
- `C:\AI\Runtime\` (untracked live MCP working state) has a near-identical name and no declared relationship.

## Notes
Created 2026-08-08 (Phase 1 Run 3, Step 3). Three open questions recorded in its README require an ADR before any code is written: separate repo vs package, migration of `design-intelligence/system/aos/`, and ownership of `C:\AI\Runtime\`.
