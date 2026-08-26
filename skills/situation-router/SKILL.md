---
name: situation-router
description: >-
  Decide which SOP/skill/workflow to invoke for the current situation before writing
  any code or spec. A minimal decision tree (codebase exists? can finish in one pass?
  need a stress-test first?) that stops agents from picking the wrong process or
  skipping straight to implementation. Free module from KI SOP Pack v1.
allowed-tools: []
version: 1.0.0
author: Keith Infinity (github.com/jalano0i9u8y7-lab)
license: MIT
compatibility: Designed for Claude Code / any agent runtime that loads SKILL.md files
tags: [router, sop, workflow, decision-tree, meta-skill]
category: workflow
---

# Situation Router

> Free module 1/4 of **KI SOP Pack v1**. Method lineage: adapted from
> [mattpocock/skills](https://github.com/mattpocock/skills) `ask-matt` router (MIT).
> This module is released standalone and free. The other three modules — To-Spec
> (chat → executable spec), Grill (plan stress-test), Skill Craft (skill-writing
> quality vocabulary) — plus the 4 upstream MIT method snapshots and a 9-slide
> onboarding deck ship together as the paid **KI SOP Pack v1** bundle ($79,
> Gumroad — link goes live shortly, watch this repo for the update).

## Why this exists

Agents that have five skills installed still guess which one applies, or skip
routing entirely and start implementing. That guess is where most wasted turns
come from: wrong SOP picked, or no SOP picked at all.

This skill is not a task-doer. It is the first five seconds of any request:
**where do I route this, before I touch anything else.**

## Decision tree

```
Does a relevant codebase / prior artifact already exist?
  NO  → run a stateless plan stress-test (ask one decision question at a time,
        propose your own recommended answer, don't implement until there is
        shared understanding) → once the plan is settled, go to spec-writing
  YES → can this be finished correctly in a single pass, with no open decisions?
          YES → implement directly
          NO  → convert the conversation into an executable spec first
                (problem statement / solution / user stories / implementation
                decisions / testing decisions / monetization or success metric /
                out of scope), THEN implement against that spec
```

## Rules

1. **Route before you build.** If you can't say which branch above you're on,
   you're not ready to write code or prose yet.
2. **Facts you can check yourself, check yourself.** Only route a question to a
   human when it's a genuine judgment call, not something discoverable by reading
   the repo/environment.
3. **One open branch at a time.** Don't run the stress-test and the spec-writer
   in parallel on the same request — resolve the tree top-to-bottom.
4. **This module doesn't write the spec or run the stress-test for you** — it
   only tells you which one to reach for. Pair it with a real spec-writing and
   stress-test process (KI SOP Pack v1's `to-spec` and `grill` modules are one
   option, built for exactly this router).

## Attribution

Underlying router pattern: mattpocock/skills (`ask-matt`), MIT License, ~188K
GitHub stars — see upstream repo for the original. This adaptation reframes it
as a standalone, tool-agnostic router skill and is distributed here under the
same MIT terms.
