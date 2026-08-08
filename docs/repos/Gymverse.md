# Gymverse

## Location
- **Local:** `C:\AI\Users\Afnad Sherief\Projects\` (not in C:\AI)
- **GitHub:** https://github.com/afnadsherief/Gymverse

## Purpose
Fitness/gamification platform with workout tracking, challenges, leaderboards, and progress analytics. PWA with tRPC backend.

## System Role
Product

## Architecture Summary
Full-stack TypeScript application:
- React + Vite + TypeScript frontend
- tRPC API layer
- Drizzle ORM + PostgreSQL
- Gamification engine (XP, streaks, plates, session-duration)
- Dockerized deployment (Railway)

## Key Modules
- `app/api/` — tRPC routers (auth, workout, progress, gamification, profile, community, exercise)
- `app/src/` — React pages (Home, Workout, Progress, Challenges, Leaderboard, etc.)
- `app/db/` — Drizzle schema + migrations
- `app/contracts/` — TypeScript type contracts
- `docs/` — Design + security docs

## Dependencies
- tRPC, Drizzle ORM, React, Vite, Tailwind CSS
- Clerk (auth)
- PostgreSQL

## Capabilities (tags)
fitness, gamification, pwa, workout-tracking, social, leaderboard

## Maturity Level
L2 Active

## Related Systems
- design-intelligence (runtime)
- park-ui / ark / ui (design references)

## Risks
- Not in C:\AI root (in user Projects directory)
- Unknown if connected to A-OS runtime

## Notes
Active development. CI configured via GitHub Actions.
