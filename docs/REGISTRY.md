# System Registry

## Core Layers

### Knowledge
- **AI-Playbook** — Canonical engineering playbook + repo intelligence (this repo)

### Control
- **AI-Orchestration** — Meta-orchestration: execution contracts, selectors, governance

### Runtime
- **design-intelligence** — A-OS v3: Autonomous Multi-Company AI Operating System (production engine)

---

## Systems Table

| System | Repo | Layer | Maturity | Status |
|--------|------|-------|----------|--------|
| A-OS Engine | design-intelligence | Runtime | L3 Production | ✅ Active |
| Meta-Orchestration | AI-Orchestration | Control | L2 Active | ⚠️ 12 unpushed commits |
| Engineering Playbook | AI-Playbook | Knowledge | L2 Active | ✅ Being aligned |
| Fitness Platform | Gymverse | Product | L2 Active | ✅ CI configured |
| Ecommerce | zeeddrops | Product | L2 Active | ⚠️ 1 unpushed commit |
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

---

## Observations

### Duplication
- **pranov-guardian + pranov**: Same wellness app split across two repos with duplicated modules (portraitEngine, sentinelEngine, triggerLogic, claudeEngine)
- **context7 + codebase-memory-mcp**: Both MCP servers for code/documentation intelligence — overlap
- **ark + park-ui + ui**: Three component libraries (unstyled, styled, radix) — design alternatives but potential confusion
- **MarketPilot + EdgePilot_Legacy**: Trading systems with unclear succession
- **park-ui nested inside ark-ui**: Duplicate reference copy

### Missing Links
- AI-Playbook does not reference actual repos (being fixed in Phase 1)
- AI-Orchestration specs don't map to design-intelligence modules
- AI-Workspace is empty skeleton — no clear purpose
- coldmail-api, naturals-salon-adoor, Splus-Bridge not documented anywhere

### Inconsistencies
- Repo naming: `ui` (shadcn), `ark` (not `ark-ui`), `park-ui` (not `park`) — inconsistent
- GitHub vs local maturity differs for AI-Orchestration
- Some repos in C:\AI, others in user home — scattered

---

## Layer Distribution
- **Knowledge**: 1 repo (AI-Playbook)
- **Control**: 1 repo (AI-Orchestration)
- **Runtime**: 1 repo (design-intelligence)
- **Product**: 11 repos (Gymverse, zeeddrops, pranov-guardian, pranov, zeedbeez-website, MarketPilot, EdgePilot_Legacy, coldmail-api, naturals-salon-adoor, Sniper-Monster, Splus-Bridge)
- **Tooling**: 10 repos (ponytail, context7, codebase-memory-mcp, github-mcp-server, humanlayer, motion, ark, park-ui, ui, playwright, vitest)
- **Unknown**: 1 repo (AI-Workspace)
