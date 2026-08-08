# zeeddrops-web (CANONICAL)

## Location
- **Local (canonical):** `C:\Projects\ZeedDrops\zeeddrops-web`
- **GitHub:** https://github.com/afnadsherief/zeeddrops-web (private, created 2026-08-08)
- **Superseded local copy:** `C:\Users\Afnad Sherief\Projects\zeeddrops\zeeddrops-web` (now isolated, remote renamed `legacy-origin`)

## Purpose
Single source of truth for the Zeed Drops web application. Next.js + TypeScript ecommerce prototype with an in-repo AI operating layer (`.ai/`) and a documentation-first `project/` architecture set.

## System Role
Product

## Architecture Summary
Next.js App Router + TypeScript. Domain-oriented `src/` layout (`domains/`, `data/`, `components/`). Carries its own governance surface: `.ai/` for agent context and `project/` for architecture documents (MASTERPLAN, COMMERCE_ARCHITECTURE, CUSTOMER_EXPERIENCE_ARCHITECTURE, KNOWLEDGE_PLATFORM_ARCHITECTURE, AI_CONTEXT, BACKLOG, AGENTS).

Two branches with **unrelated histories**:
- `feature/prototype-v2` — 95 commits, active, GitHub default branch
- `main` — 2 commits, initial scaffold, retained as fallback

## Key Modules
- `src/app/` — routes
- `src/components/` — UI components
- `src/domains/` — domain modules
- `src/data/` — data layer
- `src/hooks/`, `src/lib/`, `src/styles/`, `src/types/`
- `.ai/` — in-repo AI operating layer
- `project/` — architecture and planning documents
- `docs/` — engineering documentation
- `public/` — static assets

## Dependencies
Next.js, React, TypeScript, Tailwind (postcss), Vitest (`vitest.config.ts`), ESLint. Declared in `package.json` (`zeeddrops-web@0.1.0`).

## Capabilities (tags)
- frontend
- ecommerce
- nextjs
- product
- testing
- ai-agent

## Maturity Level
L2 Active

## Related Systems
- design-intelligence (design system runtime)
- zeeddrops (legacy business repo, isolated)
- zeeddrops-current-old (legacy scaffold, isolated)
- AI-Orchestration (control layer)

## Risks
- `main` and `feature/prototype-v2` have **unrelated histories** — they cannot be fast-forwarded into each other; a deliberate merge or branch retirement decision is still pending
- Parent directory `C:\Projects\ZeedDrops\` is **not** a git repository; `ai/`, `archive/`, `assets/`, `experiments/` siblings are untracked and unbacked-up
- Repo lives outside both `C:\AI\` and the user home, breaking the otherwise-consistent layout

## Notes
Established as canonical on 2026-08-08. Both branches pushed without force; history intact (95 commits verified against remote). Default branch on GitHub is `feature/prototype-v2`. Two older local trees were isolated rather than deleted.
