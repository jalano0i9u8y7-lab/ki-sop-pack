# KI SOP Pack v1

Turn an agent from "can chat" into "can produce a spec, stress-test a plan, and
write a skill that's actually reviewable" — four small SOP modules for Claude
Code / Hermes / any agent runtime that loads `SKILL.md` files.

Adapted from [mattpocock/skills](https://github.com/mattpocock/skills) (MIT,
~188K stars) — this is a curated 4-module selection with routing/state-machine
adaptation, not a full fork of the upstream repo.

## What's free here

- **`skills/situation-router/SKILL.md`** — the router module: decide which
  process a request needs (implement directly / stress-test first / spec first)
  before doing anything else. MIT licensed, standalone, free forever.

## What's in the paid bundle ($79, KI SOP Pack v1)

| Module | What it does |
|---|---|
| Router | Situation → correct SOP (the free module above, plus the KI adaptations) |
| To-Spec | Conversation → executable spec (problem/solution/user stories/decisions/monetization field), no interview needed |
| Grill | One-question-at-a-time plan stress-test that blocks premature "done" |
| Skill Craft | Vocabulary + structure for writing a skill that actually passes review |

Bundle also includes: 4 upstream MIT method snapshots (source-of-truth
reference copies) and a 9-slide onboarding deck.

Checkout link: launching shortly — this README will be updated with the live
URL. Until then, this repo is the free preview.

## Install the free module

Copy `skills/situation-router/SKILL.md` into `~/.claude/skills/situation-router/`
(or `.claude/skills/` in your project) and it loads like any other Claude Code
skill.

## License

`skills/situation-router/` is MIT — see [LICENSE](LICENSE). Upstream method
lineage (mattpocock/skills) is MIT; see attribution note inside the SKILL.md
frontmatter.
