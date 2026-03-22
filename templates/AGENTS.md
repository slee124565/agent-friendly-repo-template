# AGENTS.md Template

This template belongs to the starter kit of this publish repo. Its job is to help you create a root `AGENTS.md` that acts as a navigation map for humans and coding agents entering your repository.

## Design Goals

- Use root `AGENTS.md` as a navigation map, not an encyclopedia.
- Help an agent answer: what is this repo, what should I read first, and where should I go next.
- Keep workflow details in `docs/` or local guides instead of expanding root instructions indefinitely.

## Copy This As

`AGENTS.md`

## Template

```md
# AGENTS.md

## Repo Purpose
[One-line explanation of what this repository is for.]

## Start Here
1. Read `AGENTS.md` for repository-wide navigation rules.
2. Read `README.md` for the overall workspace picture.
3. Read `ARCHITECTURE.md` when you need structure boundaries and lifecycle rules.
4. Before entering a specific directory, read its local `README.md` or nested `AGENTS.md`.

## Top-Level Map
- `docs/`: stable repository-level workflows, rules, and methods
- `[active-dir]/`: active work
- `[history-dir]/`: historical context
- `[other-root-dir]/`: other repository-specific areas

## Source-of-Truth Rules
- Root `AGENTS.md` is the shared entry point; deeper guides own the details.
- Trust local `README.md` / `AGENTS.md` over filename guesses.
- `[active-dir]/` is active context by default; `[history-dir]/` is historical context by default.
- If you keep `archive/completed-tasks/`, explicitly say whether it is a full historical tree or only an index; if full snapshots live in GitHub releases, say that directly.
- `docs/` should gradually become the stable home for repo-level rules and methods.
```
