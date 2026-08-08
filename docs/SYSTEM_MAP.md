# System Map

> Generated: 2026-08-08 (Phase 1 Run 3 — System Alignment)
> Scope: all repositories discovered across `C:\AI\`, `C:\Users\Afnad Sherief\`, `C:\Projects\` and GitHub `afnadsherief`.
> This document describes **observed** state, not aspirational state. Where the two differ, both are recorded.

---

## 1. Layer Model

Five layers. Each layer may only depend downward.

| Layer | Verb | Owns | Must not |
|---|---|---|---|
| **Playbook** (Knowledge) | describes | standards, patterns, repo intelligence, glossary | execute, decide |
| **Orchestration** (Logic) | decides | contracts, selectors, governance, execution plans | execute, restate standards |
| **Runtime** (Execution) | does | plan execution, sessions, adapters, observability | decide what runs |
| **Systems** (Products) | delivers | business/product logic | re-implement orchestration |
| **Tools** (Support infra) | supports | MCP servers, testing, UI references, skills | own product logic |

```
                        ┌──────────────────────┐
                        │  PLAYBOOK            │  knowledge — describes
                        │  AI-Playbook         │
                        └──────────┬───────────┘
                                   │ standards, conventions
                                   v
                        ┌──────────────────────┐
                        │  ORCHESTRATION       │  logic — decides
                        │  AI-Orchestration    │
                        └──────────┬───────────┘
                                   │ ApprovedExecutionPlan, ContextPackage
                                   v
                        ┌──────────────────────┐
                        │  RUNTIME             │  execution — does
                        │  design-intelligence │  (de-facto)
                        │  AI-Runtime          │  (declared, empty)
                        └──────────┬───────────┘
                                   │ ExecutionResult, ArtifactMetadata
                   ┌───────────────┴───────────────┐
                   v                               v
        ┌────────────────────┐         ┌────────────────────┐
        │  SYSTEMS           │         │  TOOLS             │
        │  products          │ <-----  │  support infra     │
        └────────────────────┘         └────────────────────┘
```

---

## 2. Core Systems

| Layer | Repo | Local | Remote | Maturity |
|---|---|---|---|---|
| Knowledge | **AI-Playbook** | `C:\AI\AI-Playbook` | ✅ synced | L2 Active |
| Knowledge | **AI-HQ** | `C:\Projects\AI-HQ` | ❌ no remote | L2 Active |
| Logic | **AI-Orchestration** | `...\AI\Core\orchestration\AI-Orchestration` | ✅ synced | L2 Active |
| Execution | **design-intelligence** | `C:\AI\design-intelligence` | ✅ | L3 Production |
| Execution | **AI-Runtime** | `C:\AI\AI-Runtime` | ❌ not a repo | L0 Idea |

---

## 3. Systems (Products)

| Repo | Local | Domain |
|---|---|---|
| zeeddrops-web | `C:\Projects\ZeedDrops\zeeddrops-web` | Ecommerce — **canonical** |
| zeeddrops | `...\Projects\zeeddrops` | Ecommerce — LEGACY, isolated |
| zeeddrops-current-old | `...\Projects\zeeddrops-current-old` | Ecommerce — LEGACY, isolated |
| zeedbeez-website | `C:\AI\systems\zeedbeez-website` | Biotech wellness marketing |
| Gymverse | `C:\AI\systems\Gymverse` | Fitness / gamification |
| pranov | `C:\AI\systems\pranov` | Wellness frontend |
| pranov-guardian | `C:\AI\systems\pranov-guardian` | Wellness engine |
| MarketPilot | `C:\AI\systems\MarketPilot` | Decision intelligence (trading) |
| EdgePilot_Legacy | `C:\AI\systems\EdgePilot_Legacy` | Trading — LEGACY |
| Splus-Bridge | `C:\AI\systems\Splus-Bridge` | Trading bridge service |
| coldmail-api | `C:\AI\systems\coldmail-api` | Cold email API |
| naturals-salon-adoor | `C:\AI\systems\naturals-salon-adoor` | Static salon site |
| Sniper-Monster | `C:\AI\systems\Sniper-Monster` | Empty (L0) |
| dmitri_propfirm_engine | `C:\AI\systems\dmitri_propfirm_engine` | Empty (L0) |

---

## 4. Tools (Support Infrastructure)

| Category | Repos | Location |
|---|---|---|
| MCP servers | context7, codebase-memory-mcp, github-mcp-server, mcp-sequential-thinking | `C:\AI\Tools\MCP\` |
| Skills | ponytail (+ `ponytail-mcp`, `pi-extension`) | `C:\AI\Skills\` |
| Agent tooling | humanlayer, browser-use, opencode (archived upstream) | `C:\AI\Tools\AI\` |
| Testing | playwright, vitest | `C:\AI\Tools\Testing\` |
| Frameworks | motion | `C:\AI\Tools\Frameworks\` |
| UI reference | ui (shadcn), ark, park-ui | `C:\AI\Design\Reference\` |
| Plugin catalogue | codex-plugins | `...\.codex\.tmp\plugins` (no remote) |

All vendored third-party repos now follow: `origin` = `afnadsherief` fork, `upstream` = original.

---

## 5. Relationships

### Dependency edges
```
AI-Playbook ──describes──> every repo (via docs/repos/)
AI-Orchestration ──contracts──> AI-Runtime (planned)
AI-Orchestration ──governs──> design-intelligence (specs only, not wired)
design-intelligence ──design system──> zeeddrops-web, pranov, Gymverse, zeedbeez-website
ui / ark / park-ui ──reference──> design-intelligence
ponytail ──skills──> all agent environments
MCP servers ──context──> all agent environments
playwright / vitest ──testing──> all Node products
```

### Product ↔ runtime intent
`design-intelligence` is documented as the engine that all companies run through. **No product repository currently imports it.** The relationship is aspirational.

---

## 6. Layer Boundary Conflicts

Recorded, not resolved. Each needs an ADR.

| # | Conflict | Detail |
|---|---|---|
| 1 | **Three knowledge owners** | AI-Playbook, AI-HQ and AI-Orchestration all own governance, ADRs, standards and architecture |
| 2 | **Three runtime definitions** | `AI-Orchestration/core/execution-engine/` (stub), `design-intelligence/system/aos/` (working), `AI-Runtime/` (declared, empty) |
| 3 | **Layer naming mismatch** | Playbook uses Knowledge/Control/Runtime; Orchestration uses Executive/Knowledge/Engineering/Shared Infrastructure/Products. Neither maps onto the other |
| 4 | **Subsystem mismatch** | Orchestration names 8 subsystems (Conductor, Platform Runtime, Selector Framework, Context Engine, Memory, Governance, Execution Engine, Integrations). `design-intelligence` implements none of these names |
| 5 | **Playbook self-description stale** | `ARCHITECTURE.md` and `docs/INDEX.md` list a folder structure that omits `docs/repos/`, `REGISTRY.md`, `SYSTEM_RULES.md`, `SYSTEM_MAP.md` |
| 6 | **Orchestration owns a Playbook** | `AI-Orchestration/docs/architecture.md` lists "AI Playbook" under its own Knowledge layer, and has `playbooks/` and `knowledge/` directories |
| 7 | **Product list mismatch** | Orchestration names products ZeedBeez, Pranov, GymVerse, EdgePilot. The registry has 14 products including canonical `zeeddrops-web`, which Orchestration does not mention |
| 8 | **`design-intelligence` dual identity** | Described as both "A-OS v3 autonomous multi-company OS" (runtime) and "global design intelligence system" (design tooling). Its README claims the latter, the registry the former |
| 9 | **Directory scatter** | Repos live in `C:\AI\`, `C:\AI\systems\`, `C:\Users\...\AI\Core\`, `C:\Users\...\Projects\`, `C:\Projects\`. Five roots, no rule |
| 10 | **`C:\AI\Runtime\` vs `C:\AI\AI-Runtime\`** | Near-identical names, unrelated purposes, no declared relationship |

---

## 7. Standard Repository Structure

Applies to the three core layer repositories.

```
<repo>/
  docs/       — documentation (required)
  src/        — implementation (if applicable)
  configs/    — configuration (if applicable)
  registry/   — registries and catalogues (if applicable)
  README.md   — purpose, scope, layer relationship (required)
```

Current conformance:

| Repo | docs/ | src/ | configs/ | registry/ |
|---|---|---|---|---|
| AI-Playbook | ✅ | n/a (knowledge) | ➖ absent | ➖ uses `docs/REGISTRY.md` |
| AI-Orchestration | ✅ | ➖ uses `core/` + `sdk/` | ➖ absent | ➖ uses `core/registries/` |
| AI-Runtime | ✅ | ✅ | ✅ | ✅ |

Neither existing repo was restructured — moving `core/` or adding empty folders to live repositories was judged higher risk than the inconsistency. Conformance is recorded here for a future ADR.

---

## 8. Repository Roots

| Root | Contents | Status |
|---|---|---|
| `C:\AI\` | Playbook, design-intelligence, Runtime scaffold, Tools, Skills, Design | Primary |
| `C:\AI\systems\` | 11 product clones | Created 2026-08-08 |
| `C:\Users\...\AI\Core\` | AI-Orchestration, AI-Workspace (empty) | Split from `C:\AI\` |
| `C:\Users\...\Projects\` | zeeddrops legacy trees | Legacy, isolated |
| `C:\Projects\` | AI-HQ, ZeedDrops (canonical), empty placeholders | Undeclared until Run 3 |

`C:\Projects\` also contains empty placeholder directories `EdgePilot\`, `GymVerse\`, `Pranov\`, `Archive\` that shadow real repos in `C:\AI\systems\`.

---

## Related Documents
- [REGISTRY](./REGISTRY.md) — system registry table
- [SYSTEM_RULES](./SYSTEM_RULES.md) — ecosystem rules
- [AUDIT_FINDINGS](./AUDIT_FINDINGS.md) — drift and duplication analysis
- [repos/](./repos/) — per-repository intelligence
