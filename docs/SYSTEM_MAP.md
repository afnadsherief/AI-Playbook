# System Map

> Version: 2 — 2026-08-08 (ADR governance enforcement)
> Authority: canonical layer model defined by [ADR-0003](../adr/0003-layer-architecture.md).
> Scope: all repositories across `C:\AI\`, `C:\Users\Afnad Sherief\`, `C:\Projects\` and GitHub `afnadsherief`.
>
> **This document supersedes the 3-layer (Knowledge/Control/Runtime) and 5-layer (Playbook/Orchestration/Runtime/Systems/Tools) models. Neither is valid.**

---

## 1. Canonical Layer Model (ADR-0003)

Six layers. Every repository maps to exactly one. Dependencies flow **downward only**; L5 Tools may be consumed by any layer.

| Layer | Name | Verb | Owns | Must not |
|---|---|---|---|---|
| **L0** | Knowledge | describes | standards, ADRs, terminology, repo intelligence, strategy | decide, execute |
| **L1** | Intelligence | reasons | Prime Agent, RLM, reasoning capability | orchestrate, execute |
| **L2** | Orchestration | decides | contracts, selectors, governance application, execution plans | **execute** (ADR-0002) |
| **L3** | Runtime | executes | plan execution, sessions, adapters, observability | decide what runs |
| **L4** | Systems | delivers | product and business logic | re-implement orchestration |
| **L5** | Tools | supports | MCP servers, testing, UI references, skills, vendored infra | own product logic |

```
L0  KNOWLEDGE        AI-Playbook (AUTHORITATIVE)      describes
                     AI-HQ (strategic, subordinate)
                              │
                              v
L1  INTELLIGENCE     Prime Agent + RLM  (declared,    reasons
                     not yet populated)
                              │
                              v
L2  ORCHESTRATION    AI-Orchestration                 decides
                              │  ApprovedExecutionPlan, ContextPackage
                              v
L3  RUNTIME          design-intelligence  ── ACTIVE   executes
                     AI-Runtime           ── future
                              │  ExecutionResult, ArtifactMetadata
                              v
L4  SYSTEMS          products (14)                    delivers
                              ^
                              │ consumed by every layer
L5  TOOLS            MCP / testing / UI refs (15)     supports
```

### Governance precedence (ADR-0001)

```
AI-Playbook          AUTHORITATIVE  — sole source of standards, ADRs, terminology
   ├── AI-HQ         SUBORDINATE    — strategy and executive direction only
   └── AI-Orchestration  SUBORDINATE — execution-only, no governance authority
```

---

## 2. Core Systems

| Layer | Repo | Local | Remote | Maturity | Authority |
|---|---|---|---|---|---|
| L0 | **AI-Playbook** | `C:\AI\AI-Playbook` | ✅ synced | L2 Active | **AUTHORITATIVE** |
| L0 | **AI-HQ** | `C:\Projects\AI-HQ` | ✅ synced | L2 Active | Strategic, non-authoritative |
| L1 | *Prime Agent + RLM* | — | — | — | Declared, unpopulated |
| L2 | **AI-Orchestration** | `...\AI\Core\orchestration\AI-Orchestration` | ✅ synced | L2 Active | Controller only |
| L3 | **design-intelligence** | `C:\AI\design-intelligence` | ✅ | L3 Production | **ACTIVE RUNTIME** |
| L3 | **AI-Runtime** | `C:\AI\AI-Runtime` | ❌ not a repo | L0 Idea | Future abstraction |

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

| # | Conflict | Status | Resolution |
|---|---|---|---|
| 1 | **Three knowledge owners** — AI-Playbook, AI-HQ and AI-Orchestration all claimed governance, ADRs, standards, architecture | ✅ **RESOLVED** | [ADR-0001](../adr/0001-system-governance.md): AI-Playbook authoritative; AI-HQ strategic/non-authoritative; AI-Orchestration execution-only |
| 2 | **Three runtime definitions** — orchestration stub, `design-intelligence/system/aos/`, `AI-Runtime/` | ✅ **RESOLVED** | [ADR-0002](../adr/0002-runtime-authority.md): design-intelligence ACTIVE; AI-Runtime future abstraction; AI-Orchestration never executes |
| 3 | **Layer naming mismatch** — three incompatible models | ✅ **RESOLVED** | [ADR-0003](../adr/0003-layer-architecture.md): canonical L0–L5 model supersedes all others |
| 4 | **Subsystem mismatch** — Orchestration names 8 subsystems that design-intelligence does not implement | ⚠️ **PARTIAL** | ADR-0002 bounds it (specs describe L2 contracts only, not L3 modules). Name reconciliation deferred to a future ADR |
| 5 | **Playbook self-description stale** | ✅ **RESOLVED** | `ARCHITECTURE.md` and `docs/INDEX.md` updated 2026-08-08 |
| 6 | **Orchestration owns a Playbook** — lists "AI Playbook" under its own Knowledge layer | ✅ **RESOLVED** | ADR-0001; authority statement added to AI-Orchestration `README.md`, `AGENTS.md`, `docs/architecture.md`, `docs/governance.md` |
| 7 | **Product list mismatch** — Orchestration names 4 products, registry has 14 | ⚠️ **OPEN** | Registry (`REGISTRY.md`) is authoritative per ADR-0001. Orchestration's list is illustrative, not normative |
| 8 | **`design-intelligence` dual identity** — runtime vs design system | ✅ **RESOLVED** | ADR-0002 §6: primarily ACTIVE RUNTIME (L3); design-system assets are runtime-provided capabilities |
| 9 | **Directory scatter** — five repository roots, no placement rule | ⚠️ **OPEN** | Recorded in §8. Needs a placement ADR; no repos moved |
| 10 | **`C:\AI\Runtime\` vs `C:\AI\AI-Runtime\`** | ⚠️ **OPEN** | `C:\AI\Runtime\` = live MCP working state (untracked); `AI-Runtime\` = L3 abstraction scaffold. Relationship documented in `AI-Runtime/README.md`; rename deferred |

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

## 9. Complete Layer Mapping — All 35 Repositories

Per ADR-0003 rule 1, every repository maps to exactly one layer.

### L0 — Knowledge (2)
| Repo | Location | Authority |
|---|---|---|
| AI-Playbook | `C:\AI\AI-Playbook` | **AUTHORITATIVE** |
| AI-HQ | `C:\Projects\AI-HQ` | Strategic, non-authoritative |

### L1 — Intelligence (0)
Declared, unpopulated. Reserved for Prime Agent + RLM.

### L2 — Orchestration (1)
| Repo | Location | Note |
|---|---|---|
| AI-Orchestration | `...\AI\Core\orchestration\AI-Orchestration` | Controller only; never executes |

### L3 — Runtime (2)
| Repo | Location | Status |
|---|---|---|
| design-intelligence | `C:\AI\design-intelligence` | **ACTIVE RUNTIME** |
| AI-Runtime | `C:\AI\AI-Runtime` | Future abstraction, not active |

### L4 — Systems / Products (15)
| Repo | Location | Status |
|---|---|---|
| zeeddrops-web | `C:\Projects\ZeedDrops\zeeddrops-web` | **CANONICAL** |
| zeeddrops | `...\Projects\zeeddrops` | LEGACY, isolated |
| zeeddrops-current-old | `...\Projects\zeeddrops-current-old` | LEGACY, isolated |
| zeedbeez-website | `C:\AI\systems\zeedbeez-website` | Active |
| Gymverse | `C:\AI\systems\Gymverse` | Active |
| pranov | `C:\AI\systems\pranov` | Active |
| pranov-guardian | `C:\AI\systems\pranov-guardian` | Active |
| MarketPilot | `C:\AI\systems\MarketPilot` | Active |
| EdgePilot_Legacy | `C:\AI\systems\EdgePilot_Legacy` | LEGACY |
| Splus-Bridge | `C:\AI\systems\Splus-Bridge` | Minimal |
| coldmail-api | `C:\AI\systems\coldmail-api` | Minimal |
| naturals-salon-adoor | `C:\AI\systems\naturals-salon-adoor` | Static |
| Sniper-Monster | `C:\AI\systems\Sniper-Monster` | Empty (L0 maturity) |
| dmitri_propfirm_engine | `C:\AI\systems\dmitri_propfirm_engine` | Empty (L0 maturity) |
| AI-Workspace | `...\AI\Core\workspace\AI-Workspace` | Empty skeleton |

### L5 — Tools (15)
| Repo | Location | Category |
|---|---|---|
| ponytail | `C:\AI\Skills\ponytail` | Skills |
| context7 | `C:\AI\Tools\MCP\context7` | MCP |
| codebase-memory-mcp | `C:\AI\Tools\MCP\codebase-memory-mcp` | MCP |
| github-mcp-server | `C:\AI\Tools\MCP\github-mcp-server` | MCP |
| mcp-sequential-thinking | `C:\AI\Tools\MCP\mcp-sequential-thinking` | MCP |
| codex-plugins | `...\.codex\.tmp\plugins` | Plugins (no remote) |
| humanlayer | `C:\AI\Tools\AI\humanlayer` | Agent tooling |
| browser-use | `C:\AI\Tools\AI\browser-use` | Agent tooling |
| opencode | `C:\AI\Tools\AI\opencode` | CLI agent (upstream archived) |
| motion | `C:\AI\Tools\Frameworks\motion` | Framework |
| playwright | `C:\AI\Tools\Testing\playwright` | Testing |
| vitest | `C:\AI\Tools\Testing\vitest` | Testing |
| ui (shadcn) | `C:\AI\Design\Reference\shadcn-ui` | UI reference |
| ark | `C:\AI\Design\Reference\ark-ui` | UI reference |
| park-ui | `C:\AI\Design\Reference\park-ui` | UI reference |

**Total: 35** — L0:2, L1:0, L2:1, L3:2, L4:15, L5:15

---

## Related Documents
- [ADR-0001](../adr/0001-system-governance.md) — System Governance Model
- [ADR-0002](../adr/0002-runtime-authority.md) — Runtime Authority
- [ADR-0003](../adr/0003-layer-architecture.md) — Canonical Layer Architecture
- [REGISTRY](./REGISTRY.md) — system registry table
- [SYSTEM_RULES](./SYSTEM_RULES.md) — ecosystem rules
- [AUDIT_FINDINGS](./AUDIT_FINDINGS.md) — drift and duplication analysis
- [repos/](./repos/) — per-repository intelligence
