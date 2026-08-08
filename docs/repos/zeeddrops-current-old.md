# zeeddrops-current-old

## Location
- **Local:** `C:\Users\Afnad Sherief\Projects\zeeddrops-current-old`
- **GitHub:** none — `origin` renamed to `legacy-origin` (https://github.com/afnadsherief/zeeddrops), upstream tracking removed 2026-08-08

## Purpose
Earlier working copy of the Zeed Drops Next.js application, retained as a historical/reference snapshot.

**Status: LEGACY (do not delete)**

## System Role
Product

## Architecture Summary
Next.js (App Router) + TypeScript scaffold predating the current `zeeddrops-web` tree. Contains both a top-level `app/` directory and a `src/` tree, indicating an in-progress migration that was superseded.

## Key Modules
- `app/` — legacy route directory
- `src/app/` — routes/pages
- `src/components/` — UI components
- `src/features/` — feature modules
- `src/lib/` — utilities
- `src/services/` — service layer
- `src/types/` — shared types
- `docs/` — documentation
- `public/` — static assets

## Dependencies
Next.js, React, TypeScript. Exact versions UNKNOWN — no `package.json` at repository root at time of scan.

## Capabilities (tags)
- frontend
- ecommerce
- nextjs
- legacy

## Related Systems
- zeeddrops (parent product repo)
- zeeddrops-web (active successor)

## Maturity Level
L1 Prototype (superseded)

## Risks
- Previously shared the `afnadsherief/zeeddrops` origin with two other local trees; isolated 2026-08-08 so push collision is no longer possible.
- Directory name (`-current-old`) is self-contradictory and misleading.
- No `package.json` found at root; buildability unverified.
- Contains `node_modules/` and `.next/` — stale build artefacts on disk.

## Notes
Last commit: 2026-07-25 `Initial Next.js scaffold`. Branch `main` tracks `origin/main`. Preserved for provenance; no changes made.
