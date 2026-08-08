# pranov-guardian

## Location
- **Local:** UNKNOWN
- **GitHub:** https://github.com/afnadsherief/pranov-guardian

## Purpose
Production-grade wellness intelligence engine with pattern lifecycle, portrait timeline, ritual system, sentinel monitoring, and bounded learning. The "brain" behind the Pranov wellness platform.

## System Role
Product

## Architecture Summary
Complex TypeScript + React + Supabase application:
- Pattern lifecycle engine (learning, replay, calibration, confidence gating)
- Portrait timeline memory system
- Ritual system with ledger
- Sentinel monitoring + resolve system
- Bounded learning with data covenant
- Multi-provider AI (Claude engine, fallback router)
- PWA with offline support

## Key Modules
- `src/lib/` — 50+ TypeScript modules (airQualityEngine, arkPayload, calibration, claudeEngine, contextualLearning, dataCovenant, portraitEngine, resolveRuntime, ritualLedger, sentinelEngine, etc.)
- `src/pages/` — Arks, Guardian, Patterns, PortraitSurface, ResolveSurface, Rhythm, Rituals, Sentinel, Timeline, Settings
- `src/components/` — UI components + shadcn/ui + custom sentinels
- `src/contracts/` — Product surface contracts
- `src/integrations/supabase/` — Database client + types
- `supabase/functions/` — Edge functions (resolve, resolve-diagnostic)

## Dependencies
- React, Vite, TypeScript, Tailwind CSS
- Supabase (database + edge functions)
- shadcn/ui components
- Multi AI provider support

## Capabilities (tags)
wellness, ai-engine, pattern-recognition, learning, supabase, pwa, rituals, sentinel, monitoring

## Maturity Level
L3 Production

## Related Systems
- pranov (frontend companion)
- design-intelligence (runtime)

## Risks
- Massive codebase (400+ files) — high complexity
- Split from pranov (same app, two repos)
- Local copy not found

## Notes
The most complex product in the ecosystem. Implements sophisticated AI learning patterns with safety boundaries.
