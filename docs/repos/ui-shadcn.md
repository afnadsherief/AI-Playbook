# ui (shadcn-ui)

## Location
- **Local:** `C:\AI\Design\Reference\shadcn-ui`
- **GitHub:** https://github.com/afnadsherief/ui
- **Upstream:** https://github.com/shadcn-ui/ui

## Purpose
Beautifully designed components built with Radix UI and Tailwind CSS. Open source component distribution platform.

## System Role
Tooling

## Architecture Summary
Component library + CLI:
- React components (Radix UI based)
- CLI for component addition
- Helper packages
- Test fixtures
- Multiple framework configs (next-app, remix, vite, t3-app, etc.)
- Templates (astro-app, start-app, etc.)

## Key Modules
- `packages/shadcn/` — CLI
- `packages/react/` — React components
- `packages/helpers/` — Helper utilities
- `packages/tests/` — Test fixtures
- `apps/v4/` — v4 app
- `test/fixtures/` — Framework configs
- `templates/` — Project templates

## Dependencies
- Radix UI
- Tailwind CSS
- React

## Capabilities (tags)
ui-components, radix-ui, tailwind, cli, component-distribution

## Maturity Level
L4 Institutional

## Related Systems
- ark-ui (alternative)
- park-ui (alternative)
- design-intelligence (usage)

## Risks
- 5673 files — large fork
- Multiple framework configs to maintain

## Notes
Fork of shadcn-ui/ui. Most popular component library in ecosystem.
