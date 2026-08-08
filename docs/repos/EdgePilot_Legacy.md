# EdgePilot_Legacy

## Location
- **Local:** `C:\AI\systems\EdgePilot_Legacy` (cloned 2026-08-08)
- **GitHub:** https://github.com/afnadsherief/EdgePilot_Legacy

## Purpose
Legacy Python trading system with execution engine, market analysis, governance, risk management, and multi-provider AI routing. Superseded by MarketPilot.

## System Role
Product

## Architecture Summary
Large Python trading codebase (~500 files):
- Execution engine + lifecycle management
- Market analysis (100+ analysis modules: fvg_engine, liquidity_engine, market_structure_engine, etc.)
- AI provider routing (Moonshot, OpenRouter)
- Governance + risk management
- Replay + simulation system
- Paper trading + live execution

## Key Modules
- `ai/` — fallback_router, model_router, moonshot_client, openrouter_analyzer, provider_registry, response_normalizer
- `core/` — constants, core_stabilizer, intelligence_snapshot
- `execution/` — execution_runtime_engine, execution_states, lifecycle_monitor, live_execution_monitor
- `governance/` — compounding_engine, execution_mode_controller, governance_engine, market_open_validator
- `intelligence/` — 40+ analysis engines (adaptive_learning, confidence_engine, correlation_engine, etc.)
- `risk/` — compound_manager, exposure_manager, lot_calculator, risk_engine
- `validators/` — candlestick_engine, market_data, supportresistance_validator, vwap_engine

## Dependencies
- Python (no package manager files visible)
- TradingView parser
- Multiple AI providers

## Capabilities (tags)
trading, python, execution, market-analysis, ai-routing, risk-management, governance, replay

## Maturity Level
L2 Active (Legacy — superseded)

## Related Systems
- MarketPilot (successor)
- design-intelligence (runtime)

## Risks
- **Marketed as legacy** — unclear if still running
- No package manager files (requirements.txt exists but no lock)
- Massive codebase — 40+ intelligence engines may have duplication
- Should be archived if MarketPilot is the successor

## Notes
Most sophisticated trading system in the ecosystem. 40+ specialized analysis engines. Requires Python environment.
