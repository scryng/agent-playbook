# Commit patterns

Meta documentation for **this repository** (`agent-playbook`). When the playbook is coupled into a host project, ignore this file — use the host conventions instead.

## Authority order

1. **[Conventional Commits](https://www.conventionalcommits.org/)** — source of truth for structure and types (`feat`, `fix`, `docs`, `chore`, …).
2. **This document** — project rules on top of Conventional Commits (English infinitive, gitmoji).
3. **[Local iuricode adaptation](references/iuricode-commit-patterns.md)** — emoji/type catalog adapted from [iuricode/padroes-de-commits](https://github.com/iuricode/padroes-de-commits). Useful reference only; it must never override Conventional Commits.

## Adopted format

```
git commit -m ":emoji: type: describe the change in English using the infinitive"
```

| Part | Rule |
| ---- | ---- |
| `:emoji:` | Preferred gitmoji matching the type (see [reference](references/iuricode-commit-patterns.md)). Optional only if tooling strips it; prefer keeping it. |
| `type` | A Conventional Commits type. Required. |
| description | English, imperative/infinitive mood (“add…”, “fix…”, “document…”), concise, no trailing period on the subject line. |

Examples:

```bash
git commit -m ":tada: chore: initialize repository"
git commit -m ":books: docs: add orchestration overview and project docs boundary"
git commit -m ":sparkles: feat: add orchestrator role specification"
git commit -m ":bug: fix: correct agent dependency graph edge"
```

Expected history rendering (GitHub often expands emoji shortcodes):

```
🎉 chore: initialize repository
📚 docs: add orchestration overview and project docs boundary
✨ feat: add orchestrator role specification
🐛 fix: correct agent dependency graph edge
```

## Types (Conventional Commits)

Use these first. Mapping to semantic versioning where applicable:

| Type | Intent |
| ---- | ------ |
| `feat` | New capability (MINOR) |
| `fix` | Bug fix (PATCH) |
| `docs` | Documentation only |
| `style` | Formatting only (no behavior change) |
| `refactor` | Restructure without changing behavior |
| `perf` | Performance improvement |
| `test` | Tests only |
| `build` | Build system or dependencies |
| `ci` | CI configuration |
| `chore` | Maintenance that does not fit elsewhere |
| `revert` | Revert a previous commit |

Optional extensions from the iuricode catalog (`init`, `raw`, `cleanup`, `remove`, …) are allowed **only** when they do not conflict with Conventional Commits and the change is clearer with them. Prefer standard types when unsure.

## Hard rules for this repository

- Subject line in **English**.
- **No AI co-authorship** trailers (`Co-authored-by` for bots/assistants, generated-by footers, etc.). Commits must read as authored by the configured human git identity.
- Do not invent a git identity; configure `user.name` / `user.email` locally before the first commit (see [Setup](setup.md)).
- Prefer one logical change per commit; use the body for rationale when needed.

## Related

- [Branch management](branch-management.md)
- [Setup](setup.md)
- [Back to README](../README.md)
