# Release Notes Draft

Date: 2026-03-22

Suggested title:

`Add completed-task archive policy template`

## Summary

This update adds a practical pattern for handling completed-task history in agent-friendly repositories.

Instead of keeping full completed-task trees inside the main workspace, the template now supports:

- a thin in-repo index for completed tasks
- Git tags + GitHub release assets for full historical snapshots

This helps reduce collisions between historical material and active tools, prompts, or task directories.

## What Changed

- Added `templates/archive-release-policy.optional.md`
- Updated `templates/AGENTS.md` to clarify how `archive/completed-tasks/` should be described
- Updated `templates/ARCHITECTURE.md` to include thin-index vs release-snapshot archive strategy
- Updated `templates/ROOT-README.md` and `templates/docs-README.optional.md` to point to the optional archive policy
- Updated both English and Chinese guides to explain why completed-task history does not always belong as a full searchable tree in the main workspace

## Why This Matters

When a repository accumulates completed tasks, historical folders can start competing with active context during navigation.

For coding agents, this often shows up as:

- source-of-truth confusion
- unstable retrieval across similarly named tools and historical tasks
- unnecessary search expansion into historical material

This update makes the design more explicit:

- active context stays in the main workspace
- completed-task history can move to release snapshots
- the repository keeps only the minimum index needed for traceability

## Suggested Release Blurb

This release adds an optional completed-task archive policy to the starter kit.

If your repo uses git and GitHub as its version-history backbone, you may not want full completed-task trees to remain in the main workspace forever. The new template shows how to keep a thin in-repo index while moving full historical task snapshots into Git tags and GitHub release assets.
