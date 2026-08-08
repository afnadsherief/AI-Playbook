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

| System | Repo | Layer | Maturity | Status |
|--------|------|-------|----------|--------|
| A-OS Engine | design-intelligence | Runtime | L3 Production | ✅ Active |
| Execution Layer | AI-Runtime | Runtime | L0 Idea | ⚠️ Scaffold, not a repo |
| Meta-Orchestration | AI-Orchestration | Control | L2 Active | ✅ Synced |
| Engineering Playbook | AI-Playbook | Knowledge | L2 Active | ✅ Aligned |
| Institutional HQ | AI-HQ | Knowledge | L2 Active | ❌ No remote |
| Fitness Platform | Gymverse | Product | L2 Active | ✅ CI configured |
| Ecommerce (canonical) | zeeddrops-web | Product | L2 Active | ✅ New remote |
| Ecommerce (legacy) | zeeddrops | Product | L2 Active | ⚠️ Isolated |
| Ecommerce (legacy scaffold) | zeeddrops-current-old | Product | L1 Prototype | ⚠️ Isolated |
| Wellness Engine | pranov-guardian | Product | L3 Production | ✅ Complex |
| Wellness Frontend | pranov | Product | L2 Active | ⚠️ Split from guardian |
| Marketing Site | zeedbeez-website | Product | L2 Active | ✅ 3D/Three.js |
| Trading (current) | MarketPilot | Product | L1 Prototype | ⚠️ Doc-heavy |
| Trading (legacy) | EdgePilot_Legacy | Product | L2 Active | ⚠️ Superseded |
| Skill System | ponytail | Tooling | L3 Production | ✅ Multi-platform |
| Docs MCP | context7 | Tooling | L3 Production | ✅ Fork |
| Code Intelligence MCP | codebase-memory-mcp | Tooling | L3 Production | ✅ Fork |
| GitHub MCP | github-mcp-server | Tooling | L3 Production | ✅ Fork |
| AI Agent Tool | humanlayer | Tooling | L3 Production | ✅ Fork |
| Animation Library | motion | Tooling | L3 Production | ✅ Fork |
| UI Components (unstyled) | ark | Tooling | L4 Institutional | ✅ Fork |
| UI Components (styled) | park-ui | Tooling | L4 Institutional | ✅ Fork |
| UI Components (radix) | ui | Tooling | L4 Institutional | ✅ Fork |
| Browser Testing | playwright | Tooling | L4 Institutional | ✅ Fork |
| Unit Testing | vitest | Tooling | L4 Institutional | ✅ Fork |
| Cold Email API | coldmail-api | Product | L2 Active | ⚠️ Minimal |
| Salon Website | naturals-salon-adoor | Product | L2 Active | ⚠️ Static |
| Bridge Service | Sniper-Monster | Product | L0 Idea | ❌ Empty |
| Prop Firm Engine | dmitri_propfirm_engine | Product | L0 Idea | ❌ Empty |
| Splus Bridge | Splus-Bridge | Product | L2 Active | ⚠️ Minimal |
| Workspace Skeleton | AI-Workspace | Unknown | L0 Idea | ❌ Empty |
| Sequential Thinking MCP | mcp-sequential-thinking | Tooling | L3 Production | ✅ Fork |
| Browser Automation | browser-use | Tooling | L3 Production | ✅ Fork |
| CLI Agent (archived) | opencode | Tooling | L2 Active | ⚠️ Upstream archived |
| Codex Plugin Catalogue | codex-plugins | Tooling | L1 Prototype | ❌ No remote |

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

## Layer Distribution
- **Knowledge**: 2 (AI-Playbook, AI-HQ)
- **Control**: 1 (AI-Orchestration)
- **Runtime**: 2 (design-intelligence, AI-Runtime)
- **Product**: 14 (Gymverse, zeeddrops-web, zeeddrops, zeeddrops-current-old, pranov-guardian, pranov, zeedbeez-website, MarketPilot, EdgePilot_Legacy, coldmail-api, naturals-salon-adoor, Sniper-Monster, dmitri_propfirm_engine, Splus-Bridge)
- **Tooling**: 15 (ponytail, context7, codebase-memory-mcp, github-mcp-server, mcp-sequential-thinking, humanlayer, browser-use, opencode, motion, ark, park-ui, ui, playwright, vitest, codex-plugins)
- **Unknown**: 1 (AI-Workspace)

**Total documented: 35 repositories** (`docs/repos/`)
