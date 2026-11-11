---
name: plan-feature
description: Writes the plan for building a feature from its spec in docs/specs/, with the files it touches, the steps and what it leaves out. Use when the user asks to build, implement or add a feature that has a spec. Code written before the plan is approved is harder to review and drifts from the spec.
---

# Planning a feature

**Show the plan and stop: no code until the human approves it.**

Copy this checklist into your reply and tick it as you go:

- [ ] 1. Read the spec, docs/specs/<feature>.md. No spec → say so and
         suggest writing one first; stop. Status still draft → ask
         whether the human has approved it.
- [ ] 2. Read what AGENTS.md points to for code: docs/state.md,
         docs/hard-rules.md, docs/conventions.md, docs/decisions.md.
- [ ] 3. Write the plan in the chat: the files to create or change,
         one line each on why; the steps, in order; what you will not
         do (from Out of scope).
- [ ] 4. Does every Behavior line have a step that makes it work?
         No → back to 3.
- [ ] 5. Is there a file or a step no Behavior line needs?
         Yes → take it out (back to 3).
- [ ] 6. A new library or tool → a question in the plan, not a step.
- [ ] 7. Show the plan and stop: "Approve it, or tell me what to change."

After approval, build what the plan says. A change to the plan is asked
first, not made.
