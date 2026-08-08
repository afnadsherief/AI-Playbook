# ADR-0003: Canonical Layer Architecture

- **Status:** Accepted
- **Date:** 2026-08-08
- **Supersedes:** the 3-layer model (Knowledge/Control/Runtime) and the 5-layer model in `docs/SYSTEM_MAP.md` v1
- **Related:** [ADR-0001](./0001-system-governance.md), [ADR-0002](./0002-runtime-authority.md)

---

## Context

Three incompatible layer models were in simultaneous use:

| Source | Model |
|---|---|
| `AI-Playbook/docs/REGISTRY.md` | 3 layers: Knowledge, Control, Runtime |
| `AI-Playbook/docs/SYSTEM_MAP.md` v1 | 5 layers: Playbook, Orchestration, Runtime, Systems, Tools |
| `AI-Orchestration/docs/architecture.md` | 5 layers: Executive, Knowledge, Engineering, Shared Infrastructure, Products |

None mapped onto the others. "Knowledge" meant different things in two of them. A repository could be correctly classified in one model and unclassifiable in another. Recorded as Conflict #3 in `docs/SYSTEM_MAP.md`.

## Decision

**One canonical six-layer model. All repositories map to exactly one layer.**

| Layer | Name | Verb | Contents |
|---|---|---|---|
| **L0** | Knowledge | describes | AI-Playbook (authoritative), AI-HQ (strategic, subordinate) |
| **L1** | Intelligence | reasons | Prime Agent + RLM — reasoning and model layer |
| **L2** | Orchestration | decides | AI-Orchestration |
| **L3** | Runtime | executes | design-intelligence (active), AI-Runtime (future) |
| **L4** | Systems | delivers | Products: zeeddrops-web, MarketPilot, Gymverse, pranov, ... |
| **L5** | Tools | supports | MCP servers, testing, UI references, skills, vendored infra |

### Flow

```
L0  Knowledge      AI-Playbook  ─────────────┐  describes everything below
                   AI-HQ (strategic)         │
                          │                  │
L1  Intelligence   Prime Agent + RLM         │  reasons over knowledge
                          │                  │
L2  Orchestration  AI-Orchestration          │  decides what runs
                          │                  │
L3  Runtime        design-intelligence       │  executes (ACTIVE)
                   AI-Runtime (future)       │
                          │                  │
L4  Systems        products  <───────────────┘  delivers value
                          ^
L5  Tools          MCP / testing / UI refs      supports all layers
```

### Rules

1. **Every repository MUST map to exactly one layer.** No repository may span layers.
2. **No alternate layer models are permitted.** Any document defining a competing model must be corrected to reference this ADR.
3. **Cross-layer responsibilities are prohibited.** A repository must not perform the duties of another layer:
   - L0 must not decide or execute.
   - L2 must not execute (see ADR-0002).
   - L3 must not decide what to run.
   - L4 must not re-implement orchestration.
   - L5 must not own product logic.
4. Dependencies flow **downward only**. L5 (Tools) is the sole exception: it may be consumed by any layer.
5. Layer assignment is recorded in `docs/REGISTRY.md` and `docs/SYSTEM_MAP.md`. Both must agree.
6. Changing a repository's layer requires a new ADR.

### On L1 (Intelligence)

L1 is **declared but not yet populated**. No repository currently occupies it. It is reserved for the Prime Agent and reasoning/language-model layer. It is included in the canonical model so that reasoning capability has a defined home rather than leaking into L2 orchestration logic or L3 runtime code.

## Consequences

### Positive
- One vocabulary across the entire system; every conflict about placement now has a mechanical answer.
- Reasoning gets an explicit layer (L1) instead of being absorbed into orchestration.
- The downward-dependency rule makes architectural violations detectable by inspection.
- Supersedes both prior models cleanly rather than adding a fourth.

### Negative
- `AI-Orchestration/docs/architecture.md` defines a five-layer organisational model (Executive/Knowledge/Engineering/Shared Infrastructure/Products) that is now non-canonical. It is re-scoped by an authority statement rather than rewritten; full reconciliation is deferred.
- L1 is empty, which is a known and accepted gap.
- Some repositories sit uncomfortably in one layer (e.g. `design-intelligence` provides design-system assets used by L4 products while being L3). ADR-0002 resolves this by treating those assets as runtime-provided capabilities.

### Neutral
- No repositories were moved or restructured. Layer assignment is metadata recorded in the registry.

## Compliance

Enforced by `docs/SYSTEM_RULES.md` rules 18 and 20. Layer assignments for all 35 repositories are in `docs/REGISTRY.md`.
