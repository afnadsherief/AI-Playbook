# zeeddrops

## Location
- **Local:** `C:\Users\Afnad Sherief\Projects\zeeddrops`
- **GitHub:** https://github.com/afnadsherief/zeeddrops

## Purpose
Production-grade ecommerce platform for Zeed Drops, built with Next.js, TypeScript, and a documentation-first architecture.

## System Role
Product

## Architecture Summary
Next.js + TypeScript ecommerce parent repository. On disk the parent tree is thin (`app/`, `public/`, config files) and contains a **nested independent git repository** `zeeddrops-web/` holding the active application source.

## Key Modules
- `app/` — parent-level route directory
- `public/` — static assets
- `zeeddrops-web/` — nested repository (documented separately)
- `AGENTS.md` / `CLAUDE.md` — governance docs

## Dependencies
- Next.js, React, TypeScript
- design-intelligence (shared system)

## Capabilities (tags)
ecommerce, nextjs, frontend, design-system

## Maturity Level
L2 Active

## Related Systems
- zeeddrops-web (nested active application)
- zeeddrops-current-old (legacy scaffold, same origin)
- design-intelligence (system runtime)
- zeedbeez-website (marketing site)

## Risks
- **Nested repo conflict** — `zeeddrops-web/` has its own `.git/` and the same origin remote, with no `.gitmodules` registration
- Three local working trees push to the same remote (`zeeddrops`, `zeeddrops-web`, `zeeddrops-current-old`)
- Local branch `main` has no upstream tracking configured
- Incomplete (some pages are stubs)

## Notes
Target company for A-OS runtime.
