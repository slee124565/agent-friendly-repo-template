# ARCHITECTURE.md Template

This template belongs to the starter kit of this publish repo. Its job is to help you define the structure abstraction layer of your repository, so source-of-truth and lifecycle questions do not get overloaded into `README.md`.

## Design Goals

- Use `ARCHITECTURE.md` as the repository's structure abstraction layer.
- Explain partitioning, lifecycle, and source-of-truth boundaries.
- Avoid rewriting `README.md` or embedding detailed workflow instructions.

## Copy This As

`ARCHITECTURE.md`

## Template

```md
# ARCHITECTURE.md

This file explains the repository-level structure of `[repo-name]`.

It focuses on:

- why the repository is partitioned this way
- how content moves between areas
- which locations are usually the current source of truth

## Relationship To Other Root Files

- `README.md`
  overview and quick navigation
- `AGENTS.md`
  agent navigation and reading order

## Partition Model

- `[partition-a]`
- `[partition-b]`
- `[partition-c]`

## Content Lifecycle

1. [start state]
2. [active state]
3. [stable docs state]
4. [archive or publish state]

## Source-of-Truth Heuristics

1. Start from root `AGENTS.md` and `README.md`.
2. Use `ARCHITECTURE.md` to resolve boundary questions.
3. Once inside a directory, follow local guides.

If your repo has `archive/completed-tasks/`, make it explicit whether it is:

- a full historical tree
- or a thin index that points to release snapshots outside the main workspace

## Promotion Rules

### `[dir-a]` to `[dir-b]`

Promote content when:

- [condition 1]
- [condition 2]
- [condition 3]

### `[active-dir]` to `archive/`

When a task is completed and no longer belongs to current work:

1. Move the long-term result into `tools/`, `docs/`, an output area, or another stable location.
2. Package the full task tree as a release snapshot.
3. Keep only an index or pointer in `archive/completed-tasks/`.
```
