# Agent-Friendly Repository By Example

This walkthrough is adapted from the real `myBrainFood` workspace.

Its purpose is not to prescribe exact directory names. The goal is to show how a real repository separates:

- root entry points
- structure abstraction
- stable workflow guidance
- active versus historical context

## Four Root Files With Different Jobs

In `myBrainFood`, four root files play different roles:

- `AGENTS.md`
  agent entry point and navigation rules
- `README.md`
  repository overview
- `ARCHITECTURE.md`
  structure abstraction and source-of-truth boundaries
- `docs/README.md`
  a local guide for the `docs/` directory itself

That separation matters because a single file rarely does all of these jobs well.

## Active Context Versus Historical Context

One of the most useful structural distinctions in `myBrainFood` is not file type but work state:

- `_todos/` is active context
- `archive/` is historical context

This makes handoff and re-entry easier. When someone asks for current status, they should start from active context, not from archive or execution artifacts.

## Why `ARCHITECTURE.md` Exists

`README.md` can tell you what areas exist, but it usually does not answer questions like:

- when should an idea become a tracked task
- when should task knowledge move into `docs/`
- why published subtree mirrors are not the default source of truth

That is why `ARCHITECTURE.md` exists as a separate abstraction layer.

## What The Templates Extract

This repository turns that example into reusable files for:

- root `README.md`
- root `AGENTS.md`
- root `ARCHITECTURE.md`
- `docs/README.md`

You should adapt names and wording to your own workspace, but keep the file responsibilities clear.
