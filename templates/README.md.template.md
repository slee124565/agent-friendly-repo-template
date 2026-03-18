# README.md Template

## Design Goals

- Use root `README.md` for overview and first-pass navigation.
- Explain the main directory roles without turning the file into a full architecture manual.
- Keep structure abstraction in `ARCHITECTURE.md`, not here.

## Template

```md
# [repo-name]

[One-line description of the repository.]

## How To Read This Repo

- `README.md`
  Start here for the repository overview.
- `ARCHITECTURE.md`
  Read this when you need the partition model and source-of-truth boundaries.
- `docs/`
  Use this for repository-level workflows and stable guidance.
- `AGENTS.md`
  Use this for agent navigation and operating rules.

## Repo Structure

- `[dir-a]/`
  [One-line purpose]
- `[dir-b]/`
  [One-line purpose]
- `docs/`
  Repository-level methods, rules, and workflows

## Directory Rules

- [Content type A]: store in `[dir-a]/`
- [Content type B]: store in `[dir-b]/`
- Stable repository guidance: store in `docs/`

See `ARCHITECTURE.md` for lifecycle rules and source-of-truth boundaries.
```
