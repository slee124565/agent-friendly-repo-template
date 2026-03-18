# ARCHITECTURE.md

This file explains the repository-level structure of `agent-friendly-repo-template`.

It focuses on three questions:

- why the repository is partitioned this way
- how readers should move between the example and the reusable templates
- which files are canonical when the same idea appears in more than one place

## Relationship Between Root Files

### `README.md`

Responsible for:

- package overview
- what is included
- suggested reading order

Not responsible for:

- detailed source-of-truth rules
- explaining every template file in depth

### `AGENTS.md`

Responsible for:

- agent navigation
- first-step guidance
- repository-wide operating rules

Not responsible for:

- replacing local guides
- repeating the full architecture explanation

## Partition Model

This repository has three main zones:

- `templates/`
  The canonical reusable files
- `examples/`
  Worked examples that make the templates easier to understand
- `docs/`
  Stable guidance about this repository itself

## Content Lifecycle

1. Design ideas start from real workspace practice.
2. Reusable document shapes are extracted into `templates/`.
3. Explanatory walkthroughs are stored in `examples/`.
4. Stable rules for this repository stay in `docs/`.

## Source-of-Truth Heuristics

Use this default order:

1. Read `README.md` for package overview.
2. Read `ARCHITECTURE.md` for structure and boundaries.
3. Use `templates/` as the canonical copy source.
4. Use `examples/` to understand intent and tradeoffs, not as copy-paste authority.

## Promotion Rules

### From example insight to template file

Promote an idea into `templates/` when:

- it is reusable across repositories
- it defines a stable file responsibility
- it no longer depends on one specific workspace narrative

### From working note to `docs/`

Promote content into `docs/` when:

- it explains this repository's own operating rules
- future maintainers would need it without referring back to a task log

