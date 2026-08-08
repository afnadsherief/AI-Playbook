# zeeddrops-web

## Location
- **Local:** `C:\Users\Afnad Sherief\Projects\zeeddrops\zeeddrops-web`
- **GitHub:** https://github.com/afnadsherief/zeeddrops (same remote as parent — no dedicated repo)

## Purpose
Active Next.js 16 web application for the Zeed Drops ecommerce product. Nested inside the `zeeddrops` repository as an independent, unregistered git repository sharing the same origin remote.

## System Role
Product

## Architecture Summary
Next.js (App Router) + TypeScript application:
- Feature-based `src/` organisation
- Own test tooling (Playwright + Vitest configs present)
- Documentation-first: `docs/`, `AGENTS.md`, `CLAUDE.md` at repo root
- Own `.git/` directory; not registered as a submodule in the parent (`.gitmodules` absent)

## Key Modules
- `src/app/` — routes/pages
- `src/components/` — UI components
- `src/features/` — feature modules
- `src/hooks/` — React hooks
- `src/lib/` — utilities
- `src/services/` — service layer
- `src/styles/` — tokens, animations, typography
- `src/types/` — shared types
- `tests/` — test suites
- `docs/` — product/engineering documentation
- `public/` — static assets

## Dependencies
Next.js 16, React 19, TypeScript, Tailwind (postcss config present), Playwright, Vitest.
Exact dependency list UNKNOWN — no `package.json` at repository root at time of scan.

## Capabilities (tags)
- frontend
- ecommerce
- nextjs
- product
- testing

## Maturity Level
L2 Active

## Related Systems
- zeeddrops (parent repository, same origin)
- zeeddrops-current-old (legacy scaffold, same origin)
- design-intelligence (design system runtime)

## Risks
- **Nested repo conflict** — independent `.git/` inside `Projects\zeeddrops`, not a submodule, pushing to the same remote as the parent. High risk of divergent/overwritten history.
- Three local working trees (`zeeddrops`, `zeeddrops-web`, `zeeddrops-current-old`) all point at `afnadsherief/zeeddrops`.
- No `package.json` found at root — build entrypoint unclear from scan.
- Local branch `main` has no upstream tracking configured.

## Notes
Per `AGENTS.md`: this is **not** the Next.js commonly known — the vendored 16.x has breaking API changes; consult `node_modules/next/dist/docs/` before editing. Last commit: 2026-08-06 `docs: update AGENTS.md to reflect product state`. No restructuring performed.
