---
name: styx-combine
description: Styx Combine. Use when a task needs more than one skill and they are compatible. Combine at most 3 in sequence, never in parallel as equals, never conflicting pairs. Domain first, quality bar second, verification third. Frontend-design plus design-loop is build first, critique second. Karpathy plus TDD plus verification is code, test, check, in that order.
---

# Styx - Combine

Combine, do not dump.

Compatible pairs, in sequence:
- frontend-design, then design-loop: build, then critique
- karpathy-guidelines, then test-driven-development, then
  darren-labs-verify: code surgically, test first, verify
- rea, then frontend-design: observe, then build original
- waza-check, then verification-before-completion: review,
  then final check, not both as the same step

Incompatible pairs, never together:
- Two reviewers for the same diff
- Two full workflows, Superpowers full plus ECC full
- Two switchers, 9Router plus cc-switch
- A domain skill plus a generic skill that says the opposite

Rule: if a pair is not in the compatible list and not
obviously sequential, treat it as a clash, pick one, and
state the skipped one.
