# Architecture

High-level architecture and design principles for AI-Playbook.

## Design Principles

### 1. Documentation-First Engineering
All decisions are documented before implementation. This ensures:
- Clear reasoning for choices
- Traceable decision history
- Knowledge transferability

### 2. Modularity
Components are self-contained and independently usable:
- Each folder has a clear purpose
- Cross-references are explicit
- Dependencies are minimal

### 3. Convention Over Configuration
Standardized formats reduce cognitive load:
- Consistent file naming
- Template-based content creation
- Established patterns for common scenarios

## Repository Structure

```
docs/           — User-facing documentation
templates/      — Reusable templates
prompts/        — Prompt engineering resources
agents/         — Agent definitions and configurations
knowledge/      — Domain knowledge and patterns
adr/            — Architecture decision records
benchmarks/     — Evaluation frameworks
projects/       — Documented project implementations
security/       — Security guidelines and procedures
privacy/        — Privacy compliance materials
scripts/        — Automation and utilities
.github/        — GitHub configuration
```

## Key Decisions

See [adr/](adr/) for detailed architectural decisions.

Notable decisions:
- Document-based knowledge representation
- Markdown as primary format
- Template-driven consistency

## Extension Points

The playbook can be extended by:
1. Adding content to existing folders
2. Creating new folders with README
3. Proposing ADRs for significant changes
