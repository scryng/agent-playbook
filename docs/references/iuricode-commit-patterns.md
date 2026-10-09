# iuricode commit patterns (local adaptation)

Local English adaptation of [iuricode/padroes-de-commits](https://github.com/iuricode/padroes-de-commits), kept here so contributors do not depend on an external README at commit time.

## Adjustments vs upstream

| Upstream (iuricode) | This adaptation |
| ------------------- | --------------- |
| Portuguese prose and examples | **English** throughout |
| Emphasizes gitmoji + type catalog | Same catalog, but **[Conventional Commits](https://www.conventionalcommits.org/) wins** on type names and structure |
| Some extra types (`init`, `raw`, `cleanup`, `remove`) | Documented as **optional**; prefer standard Conventional Commits types when unclear |
| Description language unspecified | **English infinitive / imperative** subject lines |

Upstream remains the inspiration for emoji ↔ type pairing. Do not treat this file as higher authority than Conventional Commits or [commit-patterns.md](../commit-patterns.md).

## Structure

```
:emoji: type: short description in English (infinitive)
```

## Types and keywords

Aligned with Conventional Commits where possible:

| Type | Meaning |
| ---- | ------- |
| `feat` | Introduce a new feature |
| `fix` | Fix a bug |
| `docs` | Change documentation only |
| `test` | Add or change tests |
| `build` | Change build system or dependencies |
| `perf` | Improve performance |
| `style` | Change formatting only |
| `refactor` | Refactor without behavior change |
| `chore` | Perform maintenance / tooling tasks |
| `ci` | Change continuous integration |

Optional extensions (use sparingly):

| Type | Meaning |
| ---- | ------- |
| `init` | Scaffold or bootstrap (prefer `chore` / `feat` when it fits) |
| `raw` | Change configuration or data files |
| `cleanup` | Remove dead or commented code |
| `remove` | Delete obsolete files or features |

## Emoji catalog (selected)

| Intent | Emoji | Shortcode | Typical type |
| ------ | ----- | --------- | ------------ |
| Initial commit | 🎉 | `:tada:` | `chore` / `init` |
| New feature | ✨ | `:sparkles:` | `feat` |
| Bug fix | 🐛 | `:bug:` | `fix` |
| Documentation | 📚 | `:books:` | `docs` |
| Comments in code | 💡 | `:bulb:` | `docs` |
| Configuration | 🔧 | `:wrench:` | `chore` |
| Tests | 🧪 | `:test_tube:` | `test` |
| Passing test | ✅ | `:white_check_mark:` | `test` |
| Performance | ⚡ | `:zap:` | `perf` |
| Refactor | ♻️ | `:recycle:` | `refactor` |
| Build / package | 📦 | `:package:` | `build` |
| Add dependency | ➕ | `:heavy_plus_sign:` | `build` |
| Remove dependency | ➖ | `:heavy_minus_sign:` | `build` |
| CI / infra | 🧱 | `:bricks:` | `ci` |
| UI styling | 💄 | `:lipstick:` | `feat` / `style` |
| Move / rename | 🚚 | `:truck:` | `chore` |
| Cleanup | 🧹 | `:broom:` | `cleanup` / `chore` |
| Delete files | 🗑️ | `:wastebasket:` | `remove` / `chore` |
| Security | 🔒 | `:lock:` | `fix` / `feat` |
| Revert | 💥 | `:boom:` | `fix` / `revert` |
| Version tag | 🔖 | `:bookmark:` | `chore` |
| Work in progress | 🚧 | `:construction:` | (avoid on `main`) |

Full upstream tables and Portuguese text: [iuricode/padroes-de-commits](https://github.com/iuricode/padroes-de-commits).

## Examples (English)

```bash
git commit -m ":tada: chore: initialize repository"
git commit -m ":books: docs: update README overview"
git commit -m ":bug: fix: stop infinite loop on line 50"
git commit -m ":sparkles: feat: add login page"
git commit -m ":bricks: ci: adjust Dockerfile build stage"
git commit -m ":recycle: refactor: convert handlers to arrow functions"
git commit -m ":zap: perf: reduce response time for list endpoint"
```

## Attribution

Derived from work by [iuricode](https://github.com/iuricode/padroes-de-commits). See that repository for license and contribution guidelines for the original material.
