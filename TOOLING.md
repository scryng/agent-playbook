# Tooling (optional, host-owned)

This playbook does **not** require a specific OS, IDE, AI product, browser automation stack, MCP server, or plugin. Hosts differ (for example: one machine may use a canvas of agent terminals and a browser side-by-side; another may use a different agent CLI under WSL). Treat everything below as **roles**, not prescriptions.

When a host already provides a tool that fills a role, use it. When it does not, use whatever equivalent the environment has — or skip that role for the task.

## Evidence (what “done” looks like)

Abstract rules for host work. How you capture proof is up to the environment.

| Kind of change | Acceptable evidence |
| -------------- | ------------------- |
| User-facing UI | A real capture from a live run (screenshot or short recording), not a description of what should appear |
| HTTP / API | A real request and response (method, path, status, relevant body), secrets redacted |
| Data / schema | Migration or schema artifact plus a real verification step the host normally uses |
| Docs-only | No runtime evidence required |

Do not invent evidence. If you cannot exercise the change, say so in the handoff.

Commits and pull requests in a **host** repository follow that host's templates, labels, and checks — not this playbook's [docs/](docs/). Never add AI co-authorship trailers.

## Browser / interactive client (role)

**Role:** drive a real client surface to exercise and capture UI evidence.

Filled by whatever the host session already has (embedded browser, external browser automation, device/simulator portal, manual capture pasted by the user, etc.). This playbook does not name or require a product.

## Shell output hygiene (role)

**Role:** keep command output small enough to be useful in agent context.

If the host environment already compresses or filters shell output, that is fine. If not, prefer focused commands and avoid dumping unbounded logs. No specific binary is required.

## Communication brevity (role)

**Role:** optional shorter communication or commit phrasing skills installed on the host.

Never required by this playbook. Specialists remain bound by [agents/](agents/) and the orchestrator plan regardless of host shorthand skills.

## Workspace isolation (role)

**Role:** avoid colliding with other agents or live sessions in a multi-repo workspace.

Unless the task must share a live checkout, prefer a separate working copy for the change. Do not disrupt another session's branch, stash, or running app.

## What this file deliberately excludes

- Named MCP server lists or checked-in `.mcp.json` for the playbook itself
- Named AI products, IDEs, or canvas/runtime products
- Host-specific git hosts, PR label schemes, or CI workflows
- Language/stack mandates (those come from the host repo under work)

Those belong to each workspace adapter, not to this portable core.
