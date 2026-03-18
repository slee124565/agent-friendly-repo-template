# agent-friendly-repo-template

A practical guide and starter kit for building an agent-friendly repository, based on my real workspace `myBrainFood`.

This repository is not just a template pack. It is a publishable entry point built from a real workspace example.

If you are new to the idea of an agent-friendly repo, do not start from the templates first. Start from the guide, understand how `myBrainFood` split entry files, structure abstraction, local guides, and source-of-truth boundaries, then come back to the starter kit.

This repository is designed for two kinds of readers:

- people who want to understand how an agent-friendly repo grows from a real workspace
- beginners who want a simple starter kit they can adapt into their own repo

## Repository Layout

- `guide/`
  The main walkthrough, written from the perspective of a real workspace
- `templates/`
  The starter kit you can copy into your own repo

## Two Reading Paths

If you want to understand the design:

1. Read `guide/agent-friendly-repo-by-example.md` for the English guide, or `guide/agent-friendly-repo-by-example_zh.md` for the Chinese guide
2. Understand why `README.md`, `AGENTS.md`, and `ARCHITECTURE.md` are separate
3. Then inspect the files in `templates/`

If you want to start building right away:

1. Copy `templates/ROOT-README.md`, `templates/AGENTS.md`, and `templates/ARCHITECTURE.md` into your own repo
2. Rename `templates/ROOT-README.md` to `README.md`
3. Adapt the placeholder directory names to your own workspace
4. Add the optional `docs/README.md` template only when your repo starts needing stable workflow documentation

## 5-Minute Setup

1. Read `guide/agent-friendly-repo-by-example.md` once, or use `guide/agent-friendly-repo-by-example_zh.md` if you prefer Chinese.
2. Copy these files into your repository root:
   `templates/ROOT-README.md`
   `templates/AGENTS.md`
   `templates/ARCHITECTURE.md`
3. Rename `templates/ROOT-README.md` to `README.md`.
4. Replace placeholder directory names such as `[active-dir]`, `[history-dir]`, and `[dir-a]` with your real workspace structure.
5. Keep file responsibilities separate:
   `README.md` for overview,
   `AGENTS.md` for navigation,
   `ARCHITECTURE.md` for structure and source-of-truth rules.
6. Add `docs/` and `docs/README.md` only when your repo starts accumulating stable workflows or methods.
7. Add deeper local guides only after the root files are clear.

## Why This Exists

This repository comes from a simple observation: many repos have useful documents, but their responsibilities blur together. `myBrainFood` gradually evolved a clearer split between overview, navigation, structure abstraction, and stable workflow guidance.

This publish repo shares that learning in a form that others can actually reuse:

- a real workspace guide that explains why the structure exists
- a starter kit that helps beginners build a simple version of their own

## Template Roles

- `templates/ROOT-README.md`
  The overview file for your repo root
- `templates/AGENTS.md`
  The navigation file for humans and agents entering the repo
- `templates/ARCHITECTURE.md`
  The structure and source-of-truth file for boundary decisions
- `templates/docs-README.optional.md`
  An optional local guide for `docs/` once your repo needs a stable documentation area

## Optional Extension: `docs/`

The minimal starter kit keeps only these root files:

- `README.md`
- `AGENTS.md`
- `ARCHITECTURE.md`

Add a `docs/` directory only when your repository starts accumulating stable workflows, methods, operating rules, or repository-level guidance that should not stay inside a single task or feature area.

If you do add `docs/`, also add `docs/README.md` as a local guide for that directory. Its job is to explain:

- what belongs in `docs/`
- what does not belong in `docs/`
- how `docs/` relates to the root files
- where readers should start when `docs/` grows

In other words, `docs/README.md` is not a duplicate of the root `README.md`. It is a boundary and navigation file for `docs/` itself. This repository includes `templates/docs-README.optional.md` for that upgrade step.

## License

MIT
