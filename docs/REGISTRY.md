# System Registry

> Last aligned: 2026-08-08 (Phase 1 Run 3). See [SYSTEM_MAP](./SYSTEM_MAP.md) for layer definitions and conflicts.

## Core Layers

### Knowledge
- **AI-Playbook** — Canonical engineering playbook + repo intelligence (this repo)
- **AI-HQ** — Institutional headquarters documentation (`C:\Projects\AI-HQ`, no remote) ⚠️ overlapping mandate

### Control
- **AI-Orchestration** — Meta-orchestration: execution contracts, selectors, governance

### Runtime
- **design-intelligence** — A-OS v3: Autonomous Multi-Company AI Operating System (de-facto engine)
- **AI-Runtime** — Declared execution layer (`C:\AI\AI-Runtime`, scaffold only) ⚠️ not yet a repo

---

## Systems Table

**Layer** = canonical architecture layer per [ADR-0003](../adr/0003-layer-architecture.md) (L0–L5).
**Maturity** = lifecycle level per Rule 4 (L0 Idea → L4 Institutional). The two scales are independent.

| System | Repo | Layer | Maturity | Status |
|--------|------|-------|----------|--------|
| Engineering Playbook | AI-Playbook | **L0** Knowledge | L2 Active | ✅ Authoritative |
| Institutional HQ | AI-HQ | **L0** Knowledge | L2 Active | ✅ Synced (strategic, non-authoritative) |
| Prime Agent + RLM | AI-Intelligence | **L1** Intelligence | L1 Prototype | ⚠️ Not a git repo |
| Meta-Orchestration | AI-Orchestration | **L2** Orchestration | L2 Active | ✅ Synced (controller-only) |
| A-OS Engine | design-intelligence | **L3** Runtime | L3 Production | ✅ **ACTIVE RUNTIME** |
| Runtime Abstraction | AI-Runtime | **L3** Runtime | L0 Idea | ⚠️ Not active, not a repo |
| Ecommerce (canonical) | zeeddrops-web | **L4** Systems | L2 Active | ✅ Canonical |
| Ecommerce (legacy) | zeeddrops | **L4** Systems | L2 Active | ⚠️ Isolated |
| Ecommerce (legacy scaffold) | zeeddrops-current-old | **L4** Systems | L1 Prototype | ⚠️ Isolated |
| Marketing Site | zeedbeez-website | **L4** Systems | L2 Active | ✅ 3D/Three.js |
| Fitness Platform | Gymverse | **L4** Systems | L2 Active | ✅ CI configured |
| Wellness Engine | pranov-guardian | **L4** Systems | L3 Production | ✅ Complex |
| Wellness Frontend | pranov | **L4** Systems | L2 Active | ⚠️ Split from guardian |
| Trading (current) | MarketPilot | **L4** Systems | L1 Prototype | ⚠️ Doc-heavy |
| Trading (legacy) | EdgePilot_Legacy | **L4** Systems | L2 Active | ⚠️ Superseded |
| Splus Bridge | Splus-Bridge | **L4** Systems | L2 Active | ⚠️ Minimal |
| Cold Email API | coldmail-api | **L4** Systems | L2 Active | ⚠️ Minimal |
| Salon Website | naturals-salon-adoor | **L4** Systems | L2 Active | ⚠️ Static |
| Bridge Service | Sniper-Monster | **L4** Systems | L0 Idea | ❌ Empty |
| Prop Firm Engine | dmitri_propfirm_engine | **L4** Systems | L0 Idea | ❌ Empty |
| Workspace Skeleton | AI-Workspace | **L4** Systems | L0 Idea | ❌ Empty |
| Skill System | ponytail | **L5** Tools | L3 Production | ✅ Multi-platform |
| Docs MCP | context7 | **L5** Tools | L3 Production | ✅ Fork |
| Code Intelligence MCP | codebase-memory-mcp | **L5** Tools | L3 Production | ✅ Fork |
| GitHub MCP | github-mcp-server | **L5** Tools | L3 Production | ✅ Fork |
| Sequential Thinking MCP | mcp-sequential-thinking | **L5** Tools | L3 Production | ✅ Fork |
| Codex Plugin Catalogue | codex-plugins | **L5** Tools | L1 Prototype | ❌ No remote |
| AI Agent Tool | humanlayer | **L5** Tools | L3 Production | ✅ Fork |
| Browser Automation | browser-use | **L5** Tools | L3 Production | ✅ Fork |
| CLI Agent (archived) | opencode | **L5** Tools | L2 Active | ⚠️ Upstream archived |
| Animation Library | motion | **L5** Tools | L3 Production | ✅ Fork |
| Browser Testing | playwright | **L5** Tools | L4 Institutional | ✅ Fork |
| Unit Testing | vitest | **L5** Tools | L4 Institutional | ✅ Fork |
| UI Components (unstyled) | ark | **L5** Tools | L4 Institutional | ✅ Fork |
| UI Components (styled) | park-ui | **L5** Tools | L4 Institutional | ✅ Fork |
| UI Components (radix) | ui | **L5** Tools | L4 Institutional | ✅ Fork |

---

## Observations

### Duplication
- **pranov-guardian + pranov**: Same wellness app split across two repos with duplicated modules (portraitEngine, sentinelEngine, triggerLogic, claudeEngine)
- **context7 + codebase-memory-mcp**: Both MCP servers for code/documentation intelligence — overlap
- **ark + park-ui + ui**: Three component libraries (unstyled, styled, radix) — design alternatives but potential confusion
- **MarketPilot + EdgePilot_Legacy**: Trading systems with unclear succession
- **park-ui nested inside ark-ui**: Duplicate reference copy

### Missing Links
- AI-Orchestration specs don't map to design-intelligence modules (8 named subsystems, 0 implemented under those names)
- AI-Workspace is empty skeleton — no clear purpose
- AI-HQ duplicates the Playbook's knowledge mandate and has no remote
- No product repository actually imports design-intelligence — the runtime relationship is aspirational

### Inconsistencies
- Repo naming: `ui` (shadcn), `ark` (not `ark-ui`), `park-ui` (not `park`) — inconsistent
- Layer vocabulary differs between Playbook (Knowledge/Control/Runtime) and Orchestration (Executive/Knowledge/Engineering/Shared Infrastructure/Products)
- Five repository roots with no placement rule: `C:\AI\`, `C:\AI\systems\`, `C:\Users\...\AI\Core\`, `C:\Users\...\Projects\`, `C:\Projects\`
- `C:\Projects\` holds empty placeholder dirs (`EdgePilot`, `GymVerse`, `Pranov`, `Archive`) shadowing real clones in `C:\AI\systems\`
- `C:\AI\Runtime\` (live MCP state) vs `C:\AI\AI-Runtime\` (layer scaffold) — near-identical names

---

## Layer Distribution (ADR-0003)

| Layer | Count | Repos |
|---|---|---|
| **L0** Knowledge | 2 | AI-Playbook, AI-HQ |
| **L1** Intelligence | 1 | AI-Intelligence |
| **L2** Orchestration | 1 | AI-Orchestration |
| **L3** Runtime | 2 | design-intelligence (active), AI-Runtime (future) |
| **L4** Systems | 15 | zeeddrops-web, zeeddrops, zeeddrops-current-old, zeedbeez-website, Gymverse, pranov, pranov-guardian, MarketPilot, EdgePilot_Legacy, Splus-Bridge, coldmail-api, naturals-salon-adoor, Sniper-Monster, dmitri_propfirm_engine, AI-Workspace |
| **L5** Tools | 15 | ponytail, context7, codebase-memory-mcp, github-mcp-server, mcp-sequential-thinking, codex-plugins, humanlayer, browser-use, opencode, motion, playwright, vitest, ark, park-ui, ui |

**Total: 36 repositories** — all mapped, no "Unknown" layer remains, all six layers populated.
