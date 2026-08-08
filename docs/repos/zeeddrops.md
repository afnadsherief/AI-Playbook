# zeeddrops (LEGACY)

## Location
- **Local:** `C:\Users\Afnad Sherief\Projects\zeeddrops`
- **GitHub:** https://github.com/afnadsherief/zeeddrops (**no local repo now points at this remote**)
- **Remote status:** `origin` renamed to `legacy-origin`, upstream tracking removed (2026-08-08)

**Status: LEGACY (do not delete)** — superseded by `zeeddrops-web` at `C:\Projects\ZeedDrops\zeeddrops-web`.

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
- **Nested repo conflict (contained)** — `zeeddrops-web/` inside this tree still has its own `.git/`, no `.gitmodules`; both are now on `legacy-origin` with no upstream tracking, so accidental pushes are prevented
- Three divergent histories previously shared one remote; resolved by isolation, not by merge — the histories remain unreconciled
- GitHub repo `afnadsherief/zeeddrops` is now orphaned: it has content but no local tree tracking it. Decide whether to archive it.
- Incomplete (some pages are stubs)

## Notes
Target company for A-OS runtime.
