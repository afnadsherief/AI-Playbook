# pranov

## Location
- **Local:** UNKNOWN
- **GitHub:** https://github.com/afnadsherief/pranov

## Purpose
Frontend companion to pranov-guardian. Wellness platform UI with arks, resolve cards, sentinel, and trust rituals.

## System Role
Product

## Architecture Summary
React + Vite + TypeScript frontend:
- Ark cards and resolve system
- Sentinel monitoring interface
- Trust ritual onboarding
- Sound engine + atmospheric engine
- Multi-locale support
- PWA with service worker

## Key Modules
- `src/pages/` — Arks, Guardian, Onboarding, Sentinel, Settings, TrustRitual
- `src/components/` — ArkCard, BottomNav, BreathingOrb, InstallModal, PillarCard, ResolveCard, WhisperOrb
- `src/lib/` — affinityDrift, atmosphericEngine, claudeEngine, inferenceEngine, localisation, portraitEngine, progressionEngine, sentinelEngine, triggerLogic
- `src/data/` — arksData, fallbackResolves, monetisation
- `src/locales/` — i18n (English)

## Dependencies
- React, Vite, TypeScript, Tailwind CSS
- Supabase (client)
- pranov-guardian (backend engine)

## Capabilities (tags)
wellness, frontend, react, pwa, i18n, arks, resolve

## Maturity Level
L2 Active

## Related Systems
- pranov-guardian (backend engine — SAME app split across repos)
- design-intelligence (runtime)

## Risks
- **DUPLICATION:** pranov-guardian has identical modules (portraitEngine, sentinelEngine, triggerLogic, etc.)
- Same app split across two repos without clear boundary
- Code duplication likely >40%

## Notes
Should be merged with pranov-guardian or have a clearly documented API contract.
