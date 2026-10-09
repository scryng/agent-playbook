# Branch management

Meta documentation for **this repository** (`agent-playbook`). When the playbook is coupled into a host project, ignore this file — use the host conventions instead.

## Adopted pattern

**Structure:** `category/short-description`

| Category | Use |
| -------- | --- |
| `feat/` | New playbook capability (orchestrator, agents, adapters) |
| `fix/` | Bug fix |
| `docs/` | Documentation-only changes |
| `chore/` | Maintenance, tooling, repository housekeeping |
| `refactor/` | Restructure without behavior change |

Rules:

- Lowercase only
- No accents or special characters
- Spaces become `-`
- English, short, descriptive
- One category prefix, then the description — nothing else

Examples:

```
docs/readme-overview
docs/commit-patterns
docs/branch-management
docs/setup
feat/orchestrator-spec
fix/agent-index-dependency-edge
chore/add-gitignore-entries
```

## Common workflow

1. **Create a branch** from `main` (or from the PR base you intentionally stack on):

   ```bash
   git checkout main
   git pull
   git checkout -b docs/branch-management
   ```

2. **Work on the branch** — commits follow [commit patterns](commit-patterns.md).

3. **Open a pull request** into `main` (or the agreed base branch for stacked review).

4. **Merge after review** — squash or merge per reviewer preference; keep history readable.

5. **Delete the branch** after merge to avoid stale remote branches.

## Pull requests

- **Title:** English, imperative/infinitive mood, no `type:` prefix  
  Example: `Add branch management conventions`
- **Body:** include at least Summary and Test plan (checklist).
- Prefer **one concern per PR** so reviewers can approve documentation and playbook changes independently.
- Stacked PRs are fine for sequential docs (base the next branch on the previous docs branch when links depend on prior README sections).

## Recommended shape

```text
main
|-- docs/readme-overview
|   |-- docs/commit-patterns
|       |-- docs/branch-management
|           |-- docs/setup
|-- feat/…
|-- fix/…
```

Short-lived branches; `main` stays releasable documentation + playbook core.

## Related

- [Commit patterns](commit-patterns.md)
- [Setup](setup.md)
- [Back to README](../README.md)
