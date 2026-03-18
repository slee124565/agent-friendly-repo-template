# ARCHITECTURE.md Template

## Design Goals

- Use `ARCHITECTURE.md` as the repository's structure abstraction layer.
- Explain partitioning, lifecycle, and source-of-truth boundaries.
- Avoid rewriting `README.md` or embedding detailed workflow instructions.

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

## Promotion Rules

### `[dir-a]` to `[dir-b]`

Promote content when:

- [condition 1]
- [condition 2]
- [condition 3]
```
