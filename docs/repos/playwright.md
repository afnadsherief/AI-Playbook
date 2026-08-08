# playwright

## Location
- **Local:** `C:\AI\Tools\Testing\playwright`
- **GitHub:** https://github.com/afnadsherief/playwright
- **Upstream:** https://github.com/microsoft/playwright

## Purpose
Framework for Web Testing and Automation. Tests Chromium, Firefox, and WebKit with a single API.

## System Role
Tooling

## Architecture Summary
Browser automation + testing framework:
- Core engine
- Browser packages (chromium, firefox, webkit)
- Client library
- Test runner
- Trace viewer + recorder
- HTML reporter
- Dashboard
- Extension

## Key Modules
- `packages/playwright/` — Core
- `packages/playwright-core/` — Core engine
- `packages/playwright-client/` — Client API
- `packages/playwright-test/` — Test runner
- `packages/playwright-ct-core/` — Component testing
- `packages/playwright-browser-chromium/` — Chromium
- `packages/playwright-browser-firefox/` — Firefox
- `packages/playwright-browser-webkit/` — WebKit

## Dependencies
- Node.js
- Browser binaries

## Capabilities (tags)
testing, automation, browser, chromium, firefox, webkit, e2e

## Maturity Level
L4 Institutional

## Related Systems
- vitest (unit testing companion)
- zeedbeez-website (usage)

## Risks
- 3410 files — very large fork
- Browser binary management
- Upstream (microsoft) moves fast

## Notes
Fork of microsoft/playwright. Critical for e2e testing.
