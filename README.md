# agent-friendly-repo-template

An agent-friendly repository template with examples, structure guides, and source-of-truth patterns.

This repository packages a reusable set of root documents, template files, and a worked example for people who want repositories that are easier for both humans and coding agents to navigate.

## What Is Included

- `README.md`, `AGENTS.md`, `ARCHITECTURE.md`
  Root-level entry points with distinct responsibilities
- `docs/README.md`
  A local guide that explains what belongs in `docs/`
- `templates/`
  Copyable template files for the core repo entry points
- `examples/`
  A by-example walkthrough based on the real `myBrainFood` workspace

## Suggested Reading Order

1. Start with `examples/mybrainfood-walkthrough.md` to see the design in a real workspace.
2. Read `README.md` to understand the overall package.
3. Read `ARCHITECTURE.md` to understand how the repository is partitioned.
4. Copy the files in `templates/` into your own repo and adapt the directory names.

## Why This Exists

Many repositories have useful documents, but their responsibilities blur together. This package separates:

- overview
- agent navigation
- structure abstraction
- local guides for stable documentation areas

That separation reduces onboarding friction, makes source-of-truth boundaries easier to inspect, and improves recovery when a long-running task changes hands.

## Repository Layout

- `templates/`
  Reusable document skeletons
- `examples/`
  By-example walkthroughs grounded in a real workspace
- `docs/`
  Stable guidance for this repository itself

## License

MIT
