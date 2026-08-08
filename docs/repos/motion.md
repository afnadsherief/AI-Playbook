# motion

## Location
- **Local:** `C:\AI\Tools\Frameworks\motion`
- **GitHub:** https://github.com/afnadsherief/motion
- **Upstream:** https://github.com/framer/motion

## Purpose
Modern animation library for React and JavaScript. Successor to Framer Motion with improved performance and API.

## System Role
Tooling

## Architecture Summary
Animation library monorepo:
- Core animation engine
- React bindings
- DOM animations
- Motion utilities
- Cypress tests

## Key Modules
- `packages/config/` — Build configuration
- `packages/framer-motion/` — Framer Motion compatibility
- `packages/motion/` — Core library
- `packages/motion-dom/` — DOM animations
- `packages/motion-utils/` — Utilities
- `dev/` — Development examples (html, next, react, react-19)

## Dependencies
- React, JavaScript
- Cypress (testing)

## Capabilities (tags)
animation, react, framer-motion, frontend, gestures, transitions

## Maturity Level
L3 Production

## Related Systems
- zeedbeez-website (usage)
- design-intelligence (component animations)

## Risks
- 3162 files — very large fork
- Upstream (framer/motion) evolves rapidly

## Notes
Fork of framer/motion. Used in zeedbeez-website for animations.
