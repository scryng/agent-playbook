# AGENTS

Tool-agnostic entry point for this playbook. Any coding agent or IDE can start here.

## Read first

1. [ORCHESTRATOR.md](ORCHESTRATOR.md) — plan, delegate, integrate
2. [agents/INDEX.md](agents/INDEX.md) — closed roster, dependency graph, phases
3. Specialist specs under [agents/](agents/) — one file per role

## Coupling

When this repository is nested inside a host workspace:

- **Use** the files above for orchestration and specialist behavior.
- **Ignore** [docs/](docs/) — those files only govern how *this* playbook repository evolves.
- Prefer the **host** project's languages, frameworks, git/PR rules, labels, and CI. Do not impose a stack or a vendor toolchain from this playbook.

## Environment helpers

Optional, non-binding notes about evidence and local agent environment: [TOOLING.md](TOOLING.md).
