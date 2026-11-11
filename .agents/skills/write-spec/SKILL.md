---
name: write-spec
description: Writes the spec for a new feature in docs/specs/ from docs/specs/TEMPLATE.md, asking the open questions first. Use when the user wants a new feature or asks what a feature should do. Code built without an approved spec drifts from what was asked.
---

# Writing a spec

**Write no code in this task.** The human approves the spec before
anything is built.

Copy this checklist into your reply and tick it as you go:

- [ ] 1. Read docs/specs/TEMPLATE.md, docs/decisions.md and
         docs/state.md. A decision or a rejected proposal covers this
         feature → say so and ask before going on.
- [ ] 2. Ask the questions the request leaves open (at most five).
         Wait for the answers.
- [ ] 3. Write docs/specs/<feature>.md with the four sections.
- [ ] 4. Can every Behavior line be tried in the browser?
         No → rewrite it (back to 3).
- [ ] 5. Does Out of scope name what an agent would add unasked?
         No → add it (back to 3).
- [ ] 6. Show the spec and stop: "Approve it, or tell me what to change."
