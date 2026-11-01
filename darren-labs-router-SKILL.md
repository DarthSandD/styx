---
name: darren-labs-router
description: Darren Labs auto-router. Use at the start of any coding, design, or video task to pick exactly one skill from the Darren Labs library index, load only that skill, and state which skill you loaded. Never load all skills at once.
---

# Darren Labs Router

This skill is original to Darren Labs. It routes to other skills, it does
not copy their bodies, and it keeps their original credit and license
where they came from. ECC, Superpowers, Waza, and other upstream skills
remain theirs, under their licenses, and are not rebranded as Darren Labs
work.

## How to route, with clash immunity, v2

Full logic: ~/workspace/claude-skills-library/ROUTING-LOGIC.md

1. Read the task in one line. What is the user actually asking for?
2. Match it to candidates, then rank them: test evidence first,
   then specificity, then relevance, then stars, then token cost.
   Tested and passed ranks above installed but untested.
3. Clash check: if two skills claim the same primary action, load
   only the winner, state the skipped skill and the reason in one
   line. Example: waza-check wins over requesting-code-review for
   a diff review, because it is report-only and matches Darren's
   approval rules. Never load both conflicting skills.
4. Combine, at most 3, in sequence only if compatible: 1 domain
   skill, 2 quality bar (karpathy-guidelines or coding-standards,
   not both), 3 verification (darren-labs-verify or
   verification-before-completion, not both). Frontend-design
   plus design-loop is compatible in sequence, build first,
   critique second, not in parallel as equals.
5. Load only those skills. State each name and path in your first
   line of work.
6. If no row hits, proceed without a skill and say so. Never invent
   a skill name, and never load the whole library to cover a gap.

## Darren Labs rules, always on

- Bottom line first, concise, plain language. Never use the em-dash
  character.
- Think before coding, state assumptions in one line, then proceed.
- Simplicity first, minimum code, no speculative features.
- Surgical changes, touch only what the task requires.
- Verify before saying done, with the Darren Labs Verify skill.
- No external sends, publishing, GitHub push, spending, or
  irreversible change without an explicit instruction for that item.
- No secrets, keys, tokens, or passwords in output, files, or chat.
