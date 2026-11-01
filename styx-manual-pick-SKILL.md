---
name: styx-manual-pick
description: Styx Manual Pick. Use when the user names a skill, or picks from a list. Load exactly that skill, no auto override, no extra skills, no whole workflow. If the named skill clashes with an already loaded skill, say so and ask for one choice, do not load both.
---

# Styx - Manual Pick

User picks, Styx loads, Styx does not override.

1. Load exactly the named skill file.
2. State its name and path.
3. Follow only that skill, plus Styx Verify.
4. If it clashes with a skill already in use, stop, state the
   clash, and ask for one choice. Never load both.
5. If the named skill does not exist, say so, list the closest
   matches, and do not invent a skill.
