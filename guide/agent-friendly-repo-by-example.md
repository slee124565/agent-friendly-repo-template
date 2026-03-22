# Agent-Friendly Repository By Example

`A publishable walkthrough based on my real workspace, myBrainFood.`

This file is not a template. It is a public-facing case-study guide.

If you are new to the idea of an agent-friendly repository, do not start with `templates/` first. Start here. This guide explains how `myBrainFood` split entry files, structure abstraction, local guides, and actual content areas. After that, the starter kit will make much more sense.

For external readers, this is a walkthrough by example.

For beginners who want to build their own repo, this is also a bridge between understanding the design and actually starting.

This guide serves two kinds of readers:

- people who want to understand why an agent-friendly repo needs this kind of role separation
- beginners who want to start from a real workspace example and then build a simpler version of their own

One important note before reading further: directory names such as `_ideas/`, `_todos/`, `archive/`, `docs/`, and `prompts/` are the actual names used inside `myBrainFood`. They are helpful for understanding structural roles, but they are not mandatory template names. If you adopt this pattern in your own repository, you should rename things to match your own language, workflow, and conventions, as long as the underlying responsibilities remain clear.

## Start With Four Root Files

In `myBrainFood`, the root layer is split into four different roles:

- `README.md`
  The overview file for humans and agents. It answers what the workspace broadly contains.
- `AGENTS.md`
  The entry file for agents. It answers what to read first and where to find rules for different kinds of work.
- `ARCHITECTURE.md`
  The structure abstraction file. It answers how content moves, which areas are the current source of truth, and what should be promoted.
- `docs/README.md`
  The local guide for `docs/`. It answers what should go into `docs/`.

These four files form the starting point for understanding this publish repo. In other words, the starter templates did not come from abstract placeholders first. They were derived from four real responsibilities that already existed in a working workspace.

That is also the main lesson this case study wants to share: once a repo starts carrying workflows, research, outputs, and agent collaboration at the same time, a single root README becomes overloaded very quickly.

## What The Real Partitioning Of `myBrainFood` Looks Like

If you think of `myBrainFood` as a working system rather than a file bucket, several high-frequency areas reveal different roles:

- `_ideas/`
  Captures topics that are still defining the problem or shaping the hypothesis
- `_todos/`
  Holds active context: tasks, research, and planning that are currently in progress
- `archive/`
  Preserves completed or retired work that is still worth revisiting; in `myBrainFood`, completed tasks now default to thin in-repo pointers plus GitHub release snapshots instead of full historical trees
- `docs/`
  Stores stable rules, methods, and workflows
- `prompts/`
  Stores prompts that can be reused across tasks
- `tools/`
  Stores executable tools
- `publishes/`
  Stores subtree mirrors and indexes of published projects; it is not the default active source of truth

This is where recurring concepts in the design actually come from:

- workflow state
- active context vs historical context
- reusable assets
- stable docs
- external sync boundary

These are not theory-first abstractions. They are ways of describing the different roles that real directories play over time.

## The Most Important Structural Distinction: Active Context vs Historical Context

The most important structural judgment in `myBrainFood` is not file extension and not content topic. It is the current work state of the content.

The clearest example is:

- `_todos/` is active context
- `archive/` is historical context

For completed tasks, `myBrainFood` goes one step further: the main workspace keeps only a thin pointer, while the full historical tree lives in a Git tag + GitHub release snapshot. That reduces collisions between historical material and active tools or prompts.

This distinction is not just a slogan. It directly affects how handoff and re-entry work. If you need to know what is happening now, you should start from active context, not from archive or execution artifacts.

That is why an agent-friendly repo is not just about grouping files neatly. It is about making the order of source-of-truth discovery predictable.

## Why `ARCHITECTURE.md` Matters

`README.md` can usually tell you what areas exist. But it often cannot answer questions like:

- Should this content live in `_ideas/` or `_todos/`?
- When should task output be promoted into `docs/`?
- How should reusable prompts be separated from one-off task prompts?
- Why is `publishes/` not the default active source of truth?

These are practical questions in a real workspace. That is why `ARCHITECTURE.md` is not just supplementary explanation here. It is the structure abstraction layer. Its job is to make the partition model, content lifecycle, and source-of-truth boundaries explicit.

## When Something Should Not Go Into `docs/`

Many repos let `docs/` become the place where everything unclear gets dumped. `myBrainFood` tries to avoid that.

The real division of responsibilities is:

- if content still depends on a single task context, keep it with the task
- if content is only a one-off prompt draft, keep it in the task context instead of promoting it immediately
- if content is mainly a tool, put it in `tools/`
- only when content becomes stable repo-level guidance, method, or workflow should it be promoted into `docs/`

That is why this publish repo does not treat `docs/README.md` as part of the minimum required set. It is provided as an optional template instead. For beginners building their first agent-friendly repo, getting the three root files right matters more than creating an empty `docs/` directory too early.

## How The Real Example Helps You Understand The Starter Kit

If you only read templates, it is easy to mistake them for wording patterns.

The purpose of this guide is to connect the starter kit back to real structural judgments. It is meant to show:

- why root `README.md` and `AGENTS.md` should not collapse into one giant instruction file
- why `ARCHITECTURE.md` should exist independently instead of acting like an appendix to `README.md`
- why the boundary between active context and historical context directly lowers handoff cost
- why completed-task history does not always need to remain as a full searchable tree inside the main workspace
- why `docs/` and deeper local guides should appear after the repo matures, not necessarily on day one

In other words, the value of these templates is not just that they can be copied. It is that each file has a clear reason to exist.

## What Kind Of Prompts This Design Can Support

If you want to understand the practical value of an agent-friendly repo, the best approach is not abstract theory first. Look at the kinds of real prompts the repo should be able to support.

The prompts below represent questions that readers or agents are likely to ask in real work. The reason they can be answered reliably is that the repo has already made its entry points, source-of-truth boundaries, workflow pointers, and local guides explicit.

### 1. Entering The Repo For The First Time

```text
You are entering this repo for the first time. Tell me what this repo is for, what its main working areas are, and where I should look if I want to find tasks that are currently in progress.
```

This prompt tests:

- whether the root entry points are predictable
- whether `AGENTS.md` and `README.md` have clear separation of responsibility
- whether the reader is directed toward active context instead of historical areas or execution artifacts

### 2. Finding The Current Source Of Truth

```text
Help me find the current execution status of this topic and the next actions that still need to be done.
```

This prompt tests:

- whether the repo has a clear active context
- whether `archive/` is not mistaken for the current source of truth
- whether task directories contain enough state artifacts for handoff

### 3. Finding Only Long-Lived Rules

```text
Summarize the long-lived rules and methods that currently exist in this repo, and tell me where they live.
```

This prompt tests:

- whether `docs/` really carries long-lived rules
- whether execution artifacts can be handled with lazy access
- whether the root files point readers to `docs/` correctly

### 4. Entering A Specific Work Area

```text
Help me find the materials in this repo related to a specific workflow, and tell me the current status.
```

This prompt tests:

- whether readers start from the root entry points
- whether they can follow local `README.md` / `AGENTS.md` once they move deeper
- whether the repo has enough secondary entry points to prevent getting lost

### 5. Distinguishing Strong Rules From Conventions

```text
Which rules in this repo are strictly enforced, and which ones are only documentation governance conventions?
```

This prompt tests:

- whether the repo's guardrail state is visible
- whether the docs separate formal enforcement from governance convention
- whether an agent can report accurately instead of inventing mechanisms that do not exist

### 6. Taking Over A Long Task And Leaving Recoverable State

```text
Help me summarize the execution progress of a topic this month, including what is done, what is in progress, what has not started, and the recommended next steps. This summary needs to remain usable in the next session.
```

This prompt tests:

- whether the repo supports long-task state management
- whether the task contract is clear enough
- whether an agent knows not only how to answer, but also how to leave state in the correct task location

### 7. Following A Workflow Pointer To Execute Work

```text
I have a news link to analyze. Tell me which process I should use and help me start executing it.
```

This prompt tests:

- whether root `AGENTS.md` really provides workflow pointers
- whether `docs/` contains corresponding workflow files
- whether an agent follows existing process instead of reinventing the method every time

If a repo can reliably support prompts like these, it is not just a repo with many documents. It has predictable entry points, operable source-of-truth boundaries, actionable workflow entry points, and recoverable task state.

## If You Want To Build A Simpler Version Of Your Own

If you do not want to copy the whole `myBrainFood` workspace, the minimum set you can start with is:

- a root `README.md`
- a root `AGENTS.md`
- a root `ARCHITECTURE.md`

These three files are already enough to establish:

- overview
- navigation
- structure and source-of-truth rules

Then, as your repo grows, you can add:

- `docs/`
- `docs/README.md`
- `docs/archive-release-policy.md`
- deeper local guides
- workflow docs
- task contracts

That is the role of `templates/` in this publish repo: not to replicate all of `myBrainFood`, but to provide a starter kit that helps beginners build a simpler version first.

## Suggested Reading Order

If you want to actually start using this repo, I recommend this reading order:

1. Read this guide first to understand the real example and the reasons behind the design
2. Then read `templates/ROOT-README.md`
3. Then read `templates/AGENTS.md`
4. Then read `templates/ARCHITECTURE.md`
5. If your repo has already started accumulating stable workflows, then read `templates/docs-README.optional.md`
6. If completed-task history is starting to interfere with active navigation, then read `templates/archive-release-policy.optional.md`

## The Core Claim Of This Publish Guide

What this repo wants to share is not just “I have a few template files.”

It is this:

- an agent-friendly repo should make its entry points and boundaries explicit first
- the minimum viable version does not need to replicate an entire complex workspace from day one
- useful templates should be explainable by the real workspace conditions that produced them

First comes the real example, then the starter kit. That is the core design of this publish repo.

## Inspiration

The direction of this guide and starter kit was inspired by OpenAI's article `Harness engineering: leveraging Codex in an agent-first world`.

The core idea borrowed here is simple: treat `AGENTS.md` as a map rather than an encyclopedia, and let structured repository knowledge become the actual system of record.

Original source:

- OpenAI, `Harness engineering: leveraging Codex in an agent-first world`
  https://openai.com/index/harness-engineering/
