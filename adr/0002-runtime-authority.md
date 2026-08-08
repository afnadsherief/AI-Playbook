# ADR-0002: Runtime Authority

- **Status:** Accepted
- **Date:** 2026-08-08
- **Related:** [ADR-0001](./0001-system-governance.md), [ADR-0003](./0003-layer-architecture.md)

---

## Context

Three separate things claimed to be "the runtime":

| Candidate | State | Evidence |
|---|---|---|
| `AI-Orchestration/core/execution-engine/` | README stub, no implementation | 8 named subsystems incl. "Platform Runtime" and "Execution Engine" in `docs/architecture.md` |
| `design-intelligence/system/aos/` | Working orchestrator that actually executes | Registered as "A-OS v3 — Autonomous Multi-Company Intelligence System" |
| `AI-Runtime/` | Scaffold created 2026-08-08, empty | `C:\AI\AI-Runtime` |

Compounding this, `design-intelligence` has a **dual identity**: its GitHub description says "A-OS v3 — Autonomous Multi-Company Intelligence System" (a runtime) while its README says "Global, reusable, production-grade design intelligence system. NOT bound to any project" (design tooling). The registry classified it as Runtime; its own README did not.

Meanwhile AI-Orchestration specified execution behaviour it does not implement, blurring the line between deciding what runs and running it.

Recorded as Conflicts #2, #4 and #8 in `docs/SYSTEM_MAP.md`.

## Decision

**`design-intelligence` is the active runtime. `AI-Runtime` is a future abstraction layer. `AI-Orchestration` is a controller and never executes.**

| Repo | Runtime status | Maturity |
|---|---|---|
| **design-intelligence** | **ACTIVE RUNTIME** — the L3 execution system | L3 Production |
| **AI-Runtime** | **ABSTRACTION LAYER** — L3 future standardisation target, **not active** | L0 Idea |
| **AI-Orchestration** | **CONTROLLER ONLY** — decides, plans, governs; **never executes** | L2 Active |

### Rules

1. Runtime logic MUST exist only within the runtime layer (L3).
2. AI-Orchestration MUST NOT implement execution logic. Its `core/execution-engine/` and `core/platform-runtime/` may hold **contracts and specifications only**.
3. `design-intelligence` is the sole active execution target. Products execute through it.
4. `AI-Runtime` holds no executable code until a future ADR promotes it. It defines the interface that a runtime must satisfy.
5. Should `AI-Runtime` become active, `design-intelligence` execution capability migrates to it under a superseding ADR. Until then, **any statement that AI-Runtime is the runtime is incorrect.**
6. `design-intelligence` resolves its dual identity as follows: it is **primarily the active runtime (L3)**; its design-system assets (tokens, primitives, patterns) are capabilities *provided by* that runtime, not a separate identity.

### Boundary test

> If code performs an action with a side effect, it belongs in L3.
> If code chooses which action to perform, it belongs in L2.

## Consequences

### Positive
- Removes the multi-runtime conflict; one unambiguous execution target.
- Gives AI-Orchestration a clear negative constraint (never execute), making its stubs correct-by-definition rather than incomplete.
- `design-intelligence`'s dual identity is resolved without renaming or restructuring it.
- `AI-Runtime` is prevented from becoming a second empty skeleton like `AI-Workspace` — it now has a defined, bounded purpose.

### Negative
- `AI-Orchestration`'s 8-subsystem model (Conductor, Platform Runtime, Selector Framework, Context Engine, Memory, Governance, Execution Engine, Integrations) describes subsystems that do not exist in `design-intelligence` under those names. This ADR does not reconcile the naming; a future ADR must either map or rename them.
- `AI-Runtime` remains L0 with no code, which is acceptable but must be reviewed rather than left to rot.

### Neutral
- No code was written, moved or deleted. `C:\AI\Runtime\` (live MCP working state) is unaffected and remains untracked.

## Compliance

Enforced by `docs/SYSTEM_RULES.md` rules 17 and 19.
