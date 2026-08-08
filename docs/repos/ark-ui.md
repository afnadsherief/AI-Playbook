# ark-ui

## Location
- **Local:** `C:\AI\Design\Reference\ark-ui`
- **GitHub:** https://github.com/afnadsherief/ark
- **Upstream:** https://github.com/chakra-ui/ark

## Purpose
Unstyled, accessible UI components for design systems. Works with React, Vue, Solid, and Svelte. Multi-framework component library.

## System Role
Tooling

## Architecture Summary
Multi-framework component library:
- React components
- Vue components
- Solid components
- Svelte components
- CLI for project scaffolding
- Preset system
- Website + templates (next-js, nuxt, solid-start, svelte-kit)

## Key Modules
- `packages/react/` — React components
- `packages/vue/` — Vue components
- `packages/solid/` — Solid components
- `packages/svelte/` — Svelte components
- `packages/cli/` — CLI tool
- `packages/preset/` — Preset config
- `scripts/` — Build scripts
- `templates/` — Project templates
- `website/` — Documentation site

## Dependencies
- React, Vue, Solid, Svelte
- Panda CSS
- Multiple build systems

## Capabilities (tags)
ui-components, multi-framework, accessible, unstyled, design-system, cli

## Maturity Level
L4 Institutional

## Related Systems
- park-ui (companion)
- ui (shadcn — alternative)
- design-intelligence (usage)

## Risks
- 9504 files — largest fork in ecosystem
- Multi-framework complexity
- Nested park-ui inside ark-ui (possible duplicate)

## Notes
Fork of chakra-ui/ark. Reference for design-intelligence component system.
