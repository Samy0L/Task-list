# Hard rules

Read this before changing any file. Keep each rule with its reason. Add new
project-specific rules after an actual incident, with its date and explanation.

## Rules

1. Never edit docs/ai-log.md.
   Why: it is the human's own account of how AI was used. If the agent writes
   it, it stops being that.

2. Never change or skip a test to make it pass.
   Why: a green result must mean the behaviour works, not that the check was
   removed. If a test is wrong, say so and stop.

3. Never add a dependency without asking first.
   Why: every dependency is a decision the human answers for.

4. Never put secrets (passwords, API keys, tokens) in the repository or in a prompt.
   Why: what is committed or sent cannot be taken back.

No project-specific incidents have been recorded yet.
