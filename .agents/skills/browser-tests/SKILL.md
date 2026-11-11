---
name: browser-tests
description: Writes and runs the Playwright tests for a spec in docs/specs/, one test per Behavior line, following docs/testing.md. Use when the user asks to test a feature or to check that it works. A test rewritten to pass hides a broken feature.
---

# Browser tests for a spec

**A failing test is reported, never rewritten to pass.** Do not change
the app either: report what is wrong and stop.

Copy this checklist into your reply and tick it as you go:

- [ ] 1. Read docs/testing.md (Browser tests) and the spec,
         docs/specs/<feature>.md. No spec → say so and stop.
- [ ] 2. Playwright not installed yet → show the install commands
         from docs/testing.md and wait for approval (a new dependency).
- [ ] 3. Write tests/<feature>.spec.js: one test per Behavior line,
         named after it, as docs/testing.md says.
- [ ] 4. Does every Behavior line have its test, with an expect that
         fails when the behavior is broken? No → back to 3.
- [ ] 5. Run the tests with the command in docs/testing.md.
- [ ] 6. Report per Behavior line: passed or failed. For each failure:
         Expected, Received, and what in the app looks wrong.
