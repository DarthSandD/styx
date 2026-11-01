# Routing logic v2, clash immunity, great versus worst

Goal: pick the right skills from the library, combine compatible
ones, and never load conflicting ones at the same time. This file
is the logic. The router skill is the short version of it.

## Step 1: Intent in one line

Read the task, write it in one line, then match it to categories:
coding, design, video, review, research, docs, deploy, security.
If no category hits, load no skill and say so. That is the
negative test, and it passed for a poem task on 2026-11-02.

## Step 2: Rank candidates, great to worst

Score, in order, not just stars:
1. Test evidence: has this skill passed a real task test in this
   workspace? Tested and passed ranks above installed but untested,
   which ranks above parked.
2. Specificity: a skill for exactly this task wins over a generic
   skill for the whole domain.
3. Relevance to Darren: coding, design, video, review, and
   verification rank above unrelated domains.
4. Stars and recency: a tie-breaker only, never the primary score.
   Stars can be gamed, and a high-star harness can be wrong for
   a small task.
5. Token cost: a shorter, focused skill wins over a long, vague
   skill for the same task, because long files dilute compliance.

Great, tested and passed, as of 2026-11-02:
- test-driven-development: red-green run, 2 tests OK, calculator
- design-loop: picked and loaded, beautiful UI loop
- waza-check: picked and loaded, review before shipping, report-only
- context-budget: installed, clean, no secrets, no install commands
- coding-standards: installed, clean, baseline conventions
- rea, morluto: version 6.7.0, analyze-javascript-application exit 0,
  add and greet observed, 31 AST nodes, static limitation stated
- frontend-design: picked and loaded, first rule reported correctly
- karpathy-guidelines: picked, surgical test passed, is_even only
- darren-labs-router and darren-labs-verify: original to Darren Labs,
  router and verification gate, not copies of upstream skills

Good, installed but untested:
- All other ECC skills in the library, 30+ files, SKILL.md only,
  MIT repo, no hooks installed. They rank below tested skills
  until a real task test passes for each one.

Worst, parked or skipped, with reason:
- academic-pptx: proprietary license, old commits, parked
- Graphify: legit repo, no SKILL.md in its Claude folder, parked
- OpenMontage: legit repo, .md knowledge files, not SKILL.md, parked
- cc-switch: separate switcher, clash with 9Router, skipped
- deep-research, ECC: needs firecrawl and exa MCP, paid, parked
- deepseek-harness-setup, ECC: could clash with 9Router, skipped
- Any skill with a hook, installer, or paid-only core: skipped
  until that part is separately reviewed

## Step 3: Clash immunity

A clash is two skills claiming the same primary action for the
same task, or two skills with contradictory instructions.

Examples:
- Two code reviewers: waza-check and requesting-code-review.
  Pick waza-check for a diff review, because it is report-only
  and matches Darren's approval rules. Note requesting-code-review
  as skipped, do not load both.
- Two design skills: frontend-design and design-loop. These are
  compatible in sequence, not in parallel: frontend-design first
  to build, design-loop second to critique and fix. Do not load
  both at the same time as if they were equal.
- Two full workflows: Superpowers full set and ECC full harness.
  Pick one workflow per task, never both. For a small task, pick
  the single skill, not the whole workflow.
- Two switchers or harnesses: 9Router versus cc-switch, or
  darren1 versus a new DeepSeek direct setup. Skip the new one,
  keep the existing one, state the clash.
- Two TDD skills: test-driven-development and verification-loop.
  Compatible in sequence: TDD to build, verification-loop to
  check build, type, lint, tests, security grep, and diff review
  after. Do not run both as if they were the same step.

Clash rule, in order:
1. If two skills conflict, load only the winner.
2. Winner is: higher test evidence, then more specific, then
   shorter and clearer, then higher stars.
3. State the winner, state the skipped skill, and state the
   reason in one line. A silent load of both is a failure.
4. If no winner is clear, ask Darren for one choice, with the
   two options and a recommendation. Do not guess.

## Step 4: Combine compatible skills, at most 3

A task may need more than one skill, if they are compatible and
in sequence. Maximum 3 per task, in this order:
1. Domain skill, most specific: frontend-design, test-driven-
   development, rea, design-loop, etc.
2. Quality bar, if coding: karpathy-guidelines or coding-standards,
   but not both, unless one is clearly the domain skill and the
   other is the bar. Karpathy wins for surgical, minimal code.
3. Verification, if a build: darren-labs-verify or verification-
   before-completion, but not both. Darren Labs Verify wins for
   Darren's own builds, because it includes his pre-send gate.

If the domain skill already includes verification, skip step 3.
If the task is only a review, skip step 2. Never load a skill
just because it is in the library.

## Step 5: Update the ranking after each test

After every real task test, update this file:
- If a skill passed, move it to Great, with the test evidence.
- If a skill failed, or produced extra features, or touched
  unrelated files, move it down, with the failure reason.
- If a skill was parked, keep it parked, with the reason, until
  a new version or a license change justifies a re-test.
- The library grows, the ranking is what makes it usable. A
  library without ranking is just a folder.

## What this logic does not do

- It does not load all skills at once. That was tested and
  rejected: long files dilute compliance, and conflicting skills
  cancel each other out.
- It does not rebrand upstream skills as Darren Labs work.
  Upstream skills keep their original credit and license.
  Darren Labs skills are only the router and the verify gate,
  which are original to Darren.
- It does not run installers, hooks, or MCP installs. Those
  need separate approval per item.

## Update 2026-11-02, batch 3
Library 76 SKILL.md files. New ECC and Waza skills are Good,
installed but untested, below Great. data-scraper-agent is flagged:
needs a Gemini key via env var, no value in file, so it ranks
below free-core skills. Weekly cron remains newborn only.

## Update 2026-11-02, batch 4
Library 104 SKILL.md files. New motion and video skills are relevant
to Darren's video work: manim-video, motion-foundations, motion-advanced,
motion-patterns, blender-motion-state-inspection. They rank as Good
until a real video task test passes. llm-trading-agent-security is
security review only, trading execution remains user-only gated.
