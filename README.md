# Styx, by Darren Labs

Styx is a skill route, called by one command, not a separate repo and not a mega skill.

Problem it solves: a library of skills is useless if the agent
loads all of them, loads conflicting ones together, or loads a
high-star skill that is wrong for the task. Styx picks
the right skill, combines compatible ones, and skips conflicting
ones, with a reason stated every time.

## What it is

- A library: 134 SKILL.md files, as of 2026-11-02, in coding,
  design, video, review, security, deploy, and docs.
- A router: darren-labs-router, original to Darren Labs.
- A verification gate: darren-labs-verify, original to Darren Labs.
- A ranking: Great, tested and passed, versus Good, installed
  but untested, versus Parked, with a reason.
- A clash rule: at most 3 skills per task, winner only on a
  clash, skipped skill stated.

## How routing works, in 5 steps

1. Intent in one line. What is actually being asked?
2. Rank candidates. Test evidence first, then specificity,
   then relevance, then stars, then token cost. Stars alone
   never win.
3. Clash check. If two skills claim the same primary action,
   load only the winner. Example: waza-check wins over
   requesting-code-review for a diff review, because it is
   report-only and matches Darren's approval rules.
4. Combine, at most 3, in sequence only. Domain skill first,
   quality bar second, verification third. Frontend-design
   plus design-loop is build first, critique second, not
   both as equals.
5. Verify before saying done. Run the test, read the output,
   state the evidence. A reply alone is not proof.

## Great versus worst, with evidence

Great, tested and passed in this workspace:
- test-driven-development: red-green run, 2 tests OK
- design-loop: picked and loaded for a beautiful UI task
- waza-check: picked and loaded, review before shipping
- rea, by morluto: version 6.7.0, analyze exit 0, 31 AST nodes
- frontend-design, karpathy-guidelines, context-budget,
  coding-standards

Parked, with reason, not deleted:
- academic-pptx: proprietary license
- Graphify and OpenMontage: no loadable SKILL.md
- cc-switch: clashes with 9Router
- deep-research: needs paid firecrawl and exa MCP

## Credit, honestly

Styx does not rebrand other people's work. Upstream
skills, such as ECC, Superpowers, Waza, and REA, remain theirs,
under their licenses. This repo contains only Darren Labs
original work: the router, the verify gate, the routing logic,
and the index. Upstream skill bodies are not copied here.

## Install scope

SKILL.md only. No installers, no hooks, no MCP installs, no
spending, no publishing, no GitHub pushes, no external sends,
unless a separate explicit instruction approves that item.

## Status

Local skill pack, built by Muse, 2026-11-02. Styx is not a
separate GitHub repo to push. How to call it: see USAGE.md.

## Three modes, one Styx

- Styx - Auto: default. Styx picks, ranks, clashes, and combines.
- Styx - Manual Pick: user picks. Styx loads exactly that skill,
  no auto override.
- Styx - Combine: compatible skills in sequence, at most 3,
  never conflicting pairs together.

Note: Styx here is the routing system. A separate Telegram bot
with a similar name is not this repo.
