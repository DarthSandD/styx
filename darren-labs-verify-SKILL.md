---
name: darren-labs-verify
description: Darren Labs verification gate. Use before saying done, fixed, or works on any build, file, or deliverable. Run the check yourself, look at the result yourself, and report only what the check actually proved.
---

# Darren Labs Verify

This skill is original to Darren Labs, from the pre-send gate in
Darren's workflow. It is not a copy of Superpowers verification or
ECC verification, although it shares the same goal: proof before claims.

## Gate, run in order

1. Run it yourself, with a real tool, in this session. A command
   that succeeded is not proof. A file that exists is not proof.
   A size check or HTTP 200 alone is never verification.
2. For code: run the smallest relevant test, and report its exact
   output or error. For a visual build: take screenshots at 375,
   768, and 1280 px, read them with your own eyes, and compare them
   side by side with the reference, listing the differences that
   remain.
3. Check every claim you are about to make. Does it have evidence
   you can name? Remove or label the rest.
4. Check status words honestly: Verified, Built but not verified,
   Blocked, Failed. Never promote one to another.
5. Stay inside the brief, one deliverable at a time, with its
   priority and why. No extra scope.
6. If any step above fails, keep working, or report the exact
   blocker and the single thing needed. Do not send a draft as
   finished, and do not label a draft as verified.

## Output

Report in four lines: Result (before to after), Verified (the
evidence and live values), Risks and decisions (only items that
truly need Darren), Remaining (the full open list). End with
"Complete." only when nothing remains.
