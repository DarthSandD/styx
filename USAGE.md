# Styx, how to use it

Styx is NOT a separate repo. Styx is the skill route, called
by one command.

## The command

In Claude Code, and in Muse routing, call it like this:

- Styx, then your task
- /styx, then your task, in Claude Code

That one command is the entry point. You do not load 134
skills, you do not name a library file, you just call Styx.

## Three modes, under the same command

- Styx Auto: "Styx, build a landing page"
  Styx picks the skill, ranks by test evidence first, loads
  at most 3 compatible skills, winner only on a clash, and
  states the skipped skill.

- Styx Manual Pick: "Styx manual, frontend-design, build a
  landing page"
  You name the skill. Styx loads exactly that skill, no auto
  override, no extra skills.

- Styx Combine: "Styx combine, frontend-design plus design-loop,
  build a landing page"
  Styx loads compatible skills in sequence, at most 3, never
  conflicting pairs together. Build first, critique second.
  Code, test, verify, in that order.

## Examples

- "Styx, review this diff before shipping"
  Auto picks waza-check, skips requesting-code-review, with reason.

- "Styx manual, manim-video, make a simple video"
  Loads only manim-video, first rule: define the core visual
  thesis in one sentence.

- "Styx combine, karpathy plus TDD plus verify, write a todo CLI"
  Loads karpathy-guidelines, then test-driven-development, then
  darren-labs-verify, in sequence, red first, then green, then check.

## Rules, always on

- At most 3 skills per task.
- Clash: winner only, skipped skill stated.
- No skill: if no row hits, say so, do not invent a skill.
- Verify before saying done, with named evidence.
- No external sends, publishing, GitHub push, spending, or
  irreversible change without an explicit instruction for that item.

## Claude environment only, always Auto

This rule applies only in Claude Code, not in Muse, not in
other agents, and not in other sessions.

- In Claude Code, Styx always loads on Auto at the start of
  any coding, design, or video task, unless the user explicitly
  says Manual Pick or Combine.
- Great picker: rank by test evidence first, then specificity,
  then relevance, then stars, then token cost. Tested and passed
  skills rank above installed but untested, which rank above
  parked. Stars alone never win.
- If no skill hits, say so, do not invent one, do not load all.
