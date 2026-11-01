---
name: styx-auto
description: Styx Auto. Use at the start of a task when the user did not name a skill. Let Styx pick automatically from the library, rank by test evidence first, then specificity, then relevance, then stars, then token cost, load at most 3 compatible skills, winner only on a clash, state the skipped skill and reason.
---

# Styx - Auto

Default mode. You pick, the user does not.

1. Intent in one line.
2. Rank candidates, test evidence first.
3. Clash check: load only the winner, state the skipped skill.
4. Combine at most 3, in sequence: domain, quality bar, verification.
5. Verify before saying done, with Styx Verify.
