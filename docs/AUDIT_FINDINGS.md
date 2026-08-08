# Audit Findings

## Duplicates

### CRITICAL: pranov-guardian / pranov Split
- **Repos:** `pranov-guardian` + `pranov`
- **Evidence:** Both contain identical modules: `portraitEngine.ts`, `sentinelEngine.ts`, `triggerLogic.ts`, `claudeEngine.ts`, `localisation.ts`, `db/` (persist, repo, schema, sqlite)
- **Impact:** Code duplication ~40%, dual maintenance, unclear ownership
- **Fix:** Merge into single monorepo OR establish clear API contract between them

### HIGH: park-ui Nested Inside ark-ui
- **Repos:** `Design/Reference/ark-ui/park-ui/` + `Design/Reference/park-ui/`
- **Evidence:** park-ui exists both standalone AND as subdirectory of ark-ui (1735 files each)
- **Impact:** Confusion about canonical location
- **Fix:** Remove nested copy; keep only standalone

### MEDIUM: context7 / codebase-memory-mcp Overlap
- **Repos:** `context7` + `codebase-memory-mcp`
- **Evidence:** Both are MCP servers for code/documentation intelligence
- **Impact:** Unclear when to use which
- **Fix:** Document distinct use cases (context7=docs, codebase-memory=code graph)

### MEDIUM: MarketPilot / EdgePilot_Legacy Succession
- **Repos:** `MarketPilot` + `EdgePilot_Legacy`
- **Evidence:** Both trading systems; unclear if MarketPilot supersedes
- **Impact:** Two trading codebases with unclear relationship
- **Fix:** Document succession; archive EdgePilot if superseded

---

## Missing Repos

| Repo | Location | Issue |
|------|----------|-------|
| AI-Orchestration (local) | `C:\Users\Afnad Sherief\AI\Core\orchestration\AI-Orchestration` | 12 commits not on GitHub |
| zeeddrops (local) | `C:\Users\Afnad Sherief\Projects\zeeddrops` | 1 commit not on GitHub |

---

## Misplaced Repos

| Repo | Current Location | Expected | Issue |
|------|-----------------|----------|-------|
| AI-Orchestration | `C:\Users\Afnad Sherief\AI\Core\orchestration\` | `C:\AI\` or user home root | Hidden in nested path |
| AI-Workspace | `C:\Users\Afnad Sherief\AI\Core\workspace\` | Unknown | Empty skeleton |
| AI-Playbook (local) | `C:\AI\AI-Playbook` | ✅ Correct | Just cloned |
| zeeddrops | `C:\Users\Afnad Sherief\Projects\` | `C:\AI\` or user home root | Outside C:\AI |
| Gymverse | `C:\Users\Afnad Sherief\Projects\` | Unknown | Not in C:\AI |

---

## Broken Links

| Link | Status | Impact |
|------|--------|--------|
| AI-Orchestration GitHub → implementation | ❌ Broken | GitHub shows stubs, local has real code |
| Playbook → repo inventory | ❌ Missing | Being fixed in Phase 1 |
| Orchestration specs → design-intelligence | ❌ Mismatched | Specs reference non-existent modules |

---

## Structural Risks

### 1. Knowledge Drift (CRITICAL)
- AI-Orchestration local is 12 commits ahead of GitHub
- AI-Playbook doesn't list any repos
- **Risk:** Data loss, misalignment, wasted effort

### 2. Repo Scattering (MEDIUM)
- Some repos in C:\AI, others in user home Projects/AI/Core
- **Risk:** Forgotten repos, inconsistent backup

### 3. Empty Stubs (LOW)
- Sniper-Monster, dmitri_propfirm_engine, AI-Workspace are empty
- **Risk:** Namespace waste, confusion

### 4. Naming Inconsistency (LOW)
- `ui` (not shadcn-ui), `ark` (not ark-ui), `park-ui` (not park)
- **Risk:** Discovery difficulty

---

## Suggested Fixes (NO IMPLEMENTATION)

| # | Fix | Priority | Impact |
|---|-----|----------|--------|
| 1 | Push AI-Orchestration 12 commits | 🔴 CRITICAL | Prevents data loss |
| 2 | Push zeeddrops 1 commit | 🔴 CRITICAL | Prevents data loss |
| 3 | Merge pranov-guardian + pranov | 🟡 HIGH | Eliminates duplication |
| 4 | Remove nested park-ui from ark-ui | 🟡 MEDIUM | Reduces confusion |
| 5 | Archive EdgePilot_Legacy | 🟡 MEDIUM | Clarifies trading system |
| 6 | Delete empty stubs | 🟢 LOW | Cleans namespace |
| 7 | Move repos to consistent location | 🟢 LOW | Easier discovery |
| 8 | Standardize naming | 🟢 LOW | Easier discovery |
