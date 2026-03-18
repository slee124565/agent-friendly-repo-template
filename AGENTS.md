# AGENTS.md

## Repo Purpose
This repository packages an agent-friendly repo template, plus example guidance showing how the pattern works in a real workspace.

## Start Here
1. Read `AGENTS.md` to understand repository-wide navigation rules.
2. Read `README.md` for the high-level package overview.
3. Read `ARCHITECTURE.md` when you need the partition model and source-of-truth boundaries.
4. Before going deeper into a directory, read that directory's local `README.md` first.

## Top-Level Map
- `templates/`: Copyable skeletons for root-level entry files.
- `examples/`: Worked examples and walkthroughs.
- `docs/`: Stable guidance for this repository.

## Source-of-Truth Rules
- Root files explain the package itself; copied template files live under `templates/`.
- `examples/` are explanatory artifacts, not the canonical template source.
- `docs/` holds stable guidance about this repository's own rules and reading order.

## Shared Operating Rules
- Prefer concise, inspectable changes.
- Preserve role separation between overview, architecture, and agent navigation documents.
- When adapting the templates, change directory names freely but keep responsibilities explicit.

## Workflow Pointers
- `docs/README.md`: explains what belongs in `docs/` and how it relates to the root files

