# Styx

**One command to route skills. Call Styx, then your task.**

Styx picks the right skill for the job, combines compatible ones, and skips conflicting ones, with a reason every time. You do not load a whole library, and you do not guess which skill to use.

![Styx hero](styx-hero.webp)

## Quick start

In Claude Code, type:

```
Styx, build a landing page
```

Or, as a slash command:

```
/styx, build a landing page
```

That is it. Styx is the entry point. It loads at most 3 skills for that task, never all of them.

Styx works in Claude Code only, and it always loads on Auto unless you say otherwise.

## Three modes

| Mode | How to call it | What it does |
| :--- | :--- | :--- |
| Styx Auto | `Styx, build a landing page` | Default. Styx picks the skill, ranks it, and combines it if needed. |
| Styx Manual Pick | `Styx manual, frontend-design, build a landing page` | You name the skill. Styx loads exactly that one, no auto override. |
| Styx Combine | `Styx combine, frontend-design plus design-loop, build a landing page` | Compatible skills in sequence, at most 3, never conflicting pairs together. |

## Examples

- `Styx, review this diff before shipping`
  Picks waza-check, skips requesting-code-review, and says why.

- `Styx manual, manim-video, make a simple video`
  Loads only manim-video. First rule: define the core visual thesis in one sentence.

- `Styx combine, karpathy plus TDD plus verify, write a todo CLI`
  Loads karpathy-guidelines, then test-driven-development, then verify, in that order. Test first, then code, then check.

## How Styx picks, in plain language

1. Read your task in one line.
2. Rank skills by test evidence first, then by how specific they are, then by relevance, then by stars, then by token cost. Stars alone never win.
3. If two skills clash, keep only the winner, and say which one was skipped and why.
4. If no skill fits, say so. Never invent a skill, never load all of them.
5. Verify before saying done, with the exact test output as evidence.

Great means tested and passed in a real task. Good means installed but not yet tested. Parked means skipped for a reason, like a proprietary license, no loadable skill file, or a clash with an existing tool. The full ranking is in ROUTING.md.

## What is in this repo

| File | What it is |
| :--- | :--- |
| USAGE.md | How to call Styx, with examples |
| ROUTING.md | Full ranking, clash, and combine rules |
| styx-auto-SKILL.md | Auto mode skill |
| styx-manual-pick-SKILL.md | Manual Pick mode skill |
| styx-combine-SKILL.md | Combine mode skill |
| darren-labs-router-SKILL.md | Original router skill |
| darren-labs-verify-SKILL.md | Original verification gate |
| INDEX.md | Skill library index, by category |

This repo contains only Darren Labs original work. Upstream skills, such as ECC, Superpowers, Waza, and REA, remain theirs, under their licenses, and their skill bodies are not copied here.

## License

Darren Labs original files in this repo are MIT, unless a file says otherwise. Upstream skills are not in this repo, so their licenses do not apply here.
