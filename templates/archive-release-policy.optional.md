# archive-release-policy.md Optional Template

## Copy This As

`docs/archive-release-policy.md`

## When To Use

Use this when your repository has started accumulating completed tasks and you do not want full historical task trees to keep competing with active tools, prompts, or task directories inside the main workspace.

This template is especially useful when git and GitHub already provide your version history, and you want completed-task archives to become:

- a thin in-repo index
- a Git tag + GitHub release snapshot for full history

## Template

```md
# Archive Release Policy

This file defines the default archive strategy for completed tasks in `[repo-name]`.

## Default Rule

For completed tasks that no longer belong to current work:

- keep only a thin index in the main workspace
- store the full historical snapshot as a Git tag + GitHub release asset

## What Stays In The Repo

`archive/completed-tasks/` keeps:

- `README.md`
- `INDEX.md`
- optional one-page pointer stubs

## What Leaves The Repo

Do not keep these in the main workspace by default:

- full completed-task state trees
- legacy drafts, notes, and validation artifacts
- historical material that shares strong keywords with active tools or prompts

## Naming Convention

- tag: `archive/<YYYY-MM-DD>-<slug>`
- release title: `Archive Snapshot: <YYYY-MM-DD>-<slug>`
- asset filename: `<YYYY-MM-DD>-<slug>-snapshot.tar.gz`

## Close Workflow

1. Finalize the task state.
2. Make sure the long-term result already lives in `tools/`, `docs/`, an output area, or another stable location.
3. Package the full task tree as a snapshot.
4. Create a tag.
5. Create a GitHub release and upload the snapshot asset.
6. Add an entry to `archive/completed-tasks/INDEX.md`.
7. Remove the full completed-task tree from the main workspace.
```
