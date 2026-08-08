# vitest

## Location
- **Local:** `C:\AI\Tools\Testing\vitest`
- **GitHub:** https://github.com/afnadsherief/vitest
- **Upstream:** https://github.com/vitest-dev/vitest

## Purpose
Next generation testing framework powered by Vite. Fast unit testing with native ESM, TypeScript, and JSX support.

## System Role
Tooling

## Architecture Summary
Vite-native testing framework:
- Core test runner
- Browser mode
- Coverage (istanbul + v8)
- UI mode
- Snapshot testing
- Mock utilities
- Reporter
- Spy utilities

## Key Modules
- `packages/vitest/` — Core runner
- `packages/browser/` — Browser mode
- `packages/browser-playwright/` — Playwright browser integration
- `packages/coverage-istanbul/` — Istanbul coverage
- `packages/coverage-v8/` — V8 coverage
- `packages/expect/` — Assertion library
- `packages/mocker/` — Mocking
- `packages/snapshot/` — Snapshot testing
- `packages/ui/` — Web UI

## Dependencies
- Vite
- Node.js

## Capabilities (tags)
testing, unit-testing, vite, coverage, browser-testing, snapshots

## Maturity Level
L4 Institutional

## Related Systems
- playwright (e2e companion)
- zeedbeez-website (usage)

## Risks
- 3244 files — very large fork

## Notes
Fork of vitest-dev/vitest. Unit testing companion to playwright.
