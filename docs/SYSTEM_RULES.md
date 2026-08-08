# System Rules

## 1. No Silent Drift
Any change MUST update:
- Playbook (this repo)
- Registry (`/docs/REGISTRY.md`)
- Orchestration mapping (when implemented)

**Rationale:** Undetected drift between local, GitHub, and documentation caused the AI-Orchestration 12-commit gap. All changes must be reflected across all layers.

## 2. Layer Separation
- **Playbook** = knowledge only (no runtime code, no orchestration logic)
- **Orchestration** = control only (specs, contracts, governance — not execution)
- **Runtime** = execution only (design-intelligence)

**Rationale:** Mixing concerns creates coupling. Knowledge should describe, not execute.

## 3. Repo Discovery
Every repo (local or GitHub) MUST have a corresponding entry in:
- `/docs/repos/<repo-name>.md`
- `/docs/REGISTRY.md`
- `/docs/SYSTEM_MAP.md` (layer assignment)

**Rationale:** Unlisted repos are invisible repos. If it exists, it's documented. AI-HQ went undiscovered through two full discovery runs because `C:\Projects\` was outside the declared scan scope.

## 4. Maturity Tracking
Every repo MUST declare its maturity level:
- **L0 Idea** — placeholder, no implementation
- **L1 Prototype** — early code, unstable
- **L2 Active** — in development, functional
- **L3 Production** — stable, deployed, tested
- **L4 Institutional** — critical infrastructure, widely depended upon

**Rationale:** Maturity determines maintenance priority and dependency decisions.

## 5. Fork Tracking
Every fork MUST declare:
- Upstream source remote
- Last sync date
- Divergence status

**Rationale:** Forks that drift from upstream lose security patches and features.

## 6. Documentation First
No system evolves without documentation update. Before:
- Adding a module → document in Playbook
- Creating a repo → register in Playbook
- Forking a repo → declare upstream
- Archiving a repo → update Registry

## 7. Duplicate Detection
Before creating new functionality, check:
- `/docs/repos/` for existing implementations
- Capability tags for overlap
- Related systems for consolidation opportunities

**Rationale:** The pranov-guardian/pranov split and context7/codebase-memory-mcp overlap demonstrate duplication cost.

## 8. Branch Discipline
- `main` = stable, pushed, default
- `local-stable` = working state (preserved, not deleted)
- Feature branches = short-lived, deleted after merge

**Rationale:** The 12-commit AI-Orchestration gap showed the cost of unpushed work.

## 9. Cross-Repo Consistency
```
LOCAL == GITHUB == PLAYBOOK == ORCHESTRATION
```
Any mismatch MUST be flagged and resolved within 24 hours.

## 10. Empty Repo Policy
Repos with no implementation (L0) for >90 days should be:
- Populated with a purpose, OR
- Archived, OR
- Deleted

**Rationale:** Empty repos (Sniper-Monster, dmitri_propfirm_engine, AI-Workspace) create confusion and namespace waste.

## 11. Every Repo Has a Remote
Any git repository holding original work MUST have a remote. Local-only repositories are unbacked-up single points of failure.

**Rationale:** AI-HQ holds 8 commits of institutional governance documentation with no remote. `codex-plugins` lives in a deletable `.tmp` cache with no remote.

**Exception:** deliberately isolated legacy repos, which MUST use the remote name `legacy-origin` with upstream tracking removed (see Rule 12).

## 12. Legacy Isolation Protocol
A superseded repository is never deleted. It is isolated:
1. `git remote rename origin legacy-origin`
2. `git branch --unset-upstream`
3. Mark `Status: LEGACY (do not delete)` in its `docs/repos/` entry

**Rationale:** Three zeeddrops trees shared one remote with divergent histories. Isolation preserved all three histories without a merge or a force push.

## 13. One Canonical Repo Per Product
Exactly one repository is canonical per product. It is marked `(CANONICAL)` in its `docs/repos/` title. All others are LEGACY under Rule 12.

**Rationale:** Ambiguity about which zeeddrops tree was authoritative blocked a remote fix for an entire run.

## 14. Layer Vocabulary Is Single-Sourced
`docs/SYSTEM_MAP.md` is the only authority for layer names. Any repo defining its own competing layer model MUST reference the System Map or raise an ADR to change it.

**Rationale:** AI-Playbook, AI-Orchestration and AI-HQ currently define three incompatible layer models.
