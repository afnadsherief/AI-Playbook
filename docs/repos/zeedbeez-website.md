# zeedbeez-website

## Location
- **Local:** UNKNOWN
- **GitHub:** https://github.com/afnadsherief/zeedbeez-website

## Purpose
Marketing website for ZeedBeez brand. 3D/Three.js immersive experience with scroll-based storytelling, shaders, and animations.

## System Role
Product

## Architecture Summary
Next.js + Three.js + GLSL shaders marketing site:
- 3D scene management (CameraRig, LightingSystem, SceneManager, qualityManager)
- Scroll-driven storytelling engine
- GLSL shader system
- Performance-aware quality management
- Comprehensive design system documentation (30+ docs)

## Key Modules
- `src/components/` — layout, hero, features
- `src/three/` — 3D engine (camera, lighting, materials, performance, scene)
- `src/shaders/` — GLSL shader system
- `src/lib/` — scroll engine, motion timings, fonts, metadata
- `src/features/` — hero section with 3D components
- `docs/` — 30+ documentation files (architecture, design system, animation bible, etc.)

## Dependencies
- Next.js, React, TypeScript
- Three.js, GLSL
- Tailwind CSS, Framer Motion
- Playwright (e2e testing)
- Husky + lint-staged + commitlint

## Capabilities (tags)
marketing, 3d, threejs, shaders, nextjs, animation, immersive

## Maturity Level
L2 Active

## Related Systems
- zeeddrops (ecommerce)
- design-intelligence (system runtime)

## Risks
- Local copy not found
- Heavy 3D — performance considerations
- Many empty directories (services, store, shaders) — incomplete

## Notes
Sophisticated marketing site with production-grade tooling (commitlint, husky, e2e).
