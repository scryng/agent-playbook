# Setup

Meta documentation for **this repository** (`agent-playbook`). When the playbook is coupled into a host project, ignore this file — use the host setup instead.

This guide covers developing and reviewing **agent-playbook** itself. It stays tool-agnostic: any Git host client (`gh`, Azure DevOps CLI, plain Git), any OS, and any AI coding assistant can be used as long as the conventions in `docs/` are followed when changing this repo.

## Prerequisites

- Git
- Access to the private repository
- A configured Git identity for this checkout (local config preferred over a forced global default)

## Clone

```bash
git clone https://github.com/scryng/agent-playbook.git
cd agent-playbook
```

SSH works the same way if your keys are set up for the hosting account.

## Configure Git identity (required before first commit)

Verify:

```bash
git config user.name
git config user.email
```

If either is empty, set them **locally** in this repository (do not invent a placeholder identity):

```bash
git config user.name "YOUR_NAME"
git config user.email "YOUR_EMAIL"
```

If you use a profile helper (for example a shell function that maps a short profile name to name/email), run it from the repository root so the values land in local config for this checkout only.

## Branch, commit, and pull request

1. Create a branch per [branch management](branch-management.md).
2. Commit per [commit patterns](commit-patterns.md) (Conventional Commits + English infinitive; no AI co-authorship).
3. Push and open a PR for review.
4. Delete the branch after merge.

Example:

```bash
git checkout main
git pull
git checkout -b docs/setup
# edit files…
git add .
git commit -m ":books: docs: add local setup guide"
git push -u origin HEAD
```

## Coupling into a host project (preview)

Typical host layout (exact folder name is up to the host team):

```text
host-project/
├── .gitignore          # ignore the playbook path
├── …                   # host source
└── agent-playbook/     # or .agents/agent-playbook/ — nested clone
```

1. Clone this repository into the chosen path inside the host project.
2. Add that path to the host `.gitignore` so the host history does not track nested playbook commits.
3. Point your orchestrator/agents at the **playbook core** paths only.
4. **Do not** load or enforce anything under `docs/` on the host — those files govern this repository’s evolution only.

Orchestration specs (orchestrator role, agent roster, host-facing conventions) will land outside `docs/` in follow-up work.

## Verify

- [ ] `git config user.name` and `user.email` are set in this checkout
- [ ] You can create a `docs/…` or `feat/…` branch from `main`
- [ ] A test commit message matches `:emoji: type: english infinitive subject`
- [ ] You understand that `docs/` is ignored when this playbook is coupled into another project

## Related

- [Commit patterns](commit-patterns.md)
- [Branch management](branch-management.md)
- [Back to README](../README.md)
