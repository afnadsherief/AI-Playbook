# AI-Intelligence

## Location
- **Local:** `C:\AI\AI-Intelligence`
- **GitHub:** ❌ Not on GitHub — not yet a git repository

## Purpose
The L1 Intelligence layer. Classifies incoming requests, selects a model and tool, and hands a routing decision to the orchestration layer. Reasons; does not execute.

## System Role
L1 Intelligence (ADR-0003) — Prime Agent + RLM

## Architecture Summary
V1: passive, rule-based, zero dependencies. Four modules and a linear integration flow:

```
input -> Prime Agent (classify, select) -> Harness (evaluate) -> RLM (log) -> result
```

Every decision terminates in `execution_plan: "pass_to_orchestration"`. No execution occurs in this layer.

Built at `C:\AI\AI-Intelligence` rather than the requested `C:\AI\AI-Runtime` because ADR-0003 rule 3 prohibits cross-layer responsibilities and ADR-0002 rule 4 keeps AI-Runtime code-free.

## Key Modules
- `src/prime-agent/agent.ts` — `classify`, `selectModel`, `selectTool`, `handleRequest`
- `src/harness/harness.ts` — `evaluate` → `pass` / `partial` / `fail` + score 0–1
- `src/rlm/rlm.ts` — `logExperience`, append-only
- `src/memory/memory.ts` — `readLogs`, `writeLog` (plain JSON)
- `src/index.ts` — integration flow + CLI entrypoint
- `configs/agent.config.json` — passive / learning disabled / rule-based
- `docs/INTELLIGENCE_LAYER.md` — layer documentation
- `logs/rlm-log.json` — experience log

## Dependencies
None. TypeScript on `node:fs` / `node:path` only. No frameworks, no database, no external APIs. Executed with `bun`.

## Capabilities (tags)
- ai-agent
- classification
- evaluation
- logging
- intelligence

## Maturity Level
L1 Prototype

## Related Systems
- AI-Orchestration (L2 — intended handoff target, not yet wired)
- design-intelligence (L3 — active runtime)
- AI-Playbook (L0 — governing authority)

## Risks
- **Not a git repository** — violates SYSTEM_RULES rule 11; no remote, no backup
- **Not wired to L2** — `pass_to_orchestration` is a literal string, not a call. AI-Orchestration is unaware this layer exists
- Config file is versioned but not read at runtime; V1 behaviour is hardcoded to match it
- Model and tool selection are stubs returning constants
- Classification is first-match-wins keyword matching; "document the code" misclassifies as `code`
- `writeLog` does unlocked read-modify-write — concurrent writes can lose records
- Log grows unbounded, no rotation
- No automated tests

## Notes
Created 2026-08-08. Fills the previously empty L1 slot in the canonical layer model. Verified manually: classification across 4 task types, all three harness branches (`fail` on empty / non-object / no fields, `partial` at 0.25, `pass` at 1.0), and append-only logging across consecutive runs.
