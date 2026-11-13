# Task List

Task List is a planned to-do web application with user accounts, tasks and
administration. Its frontend direction is Vue + Vite + TypeScript + Tailwind CSS.
The development environment runs in Docker. Application implementation is still
pending; the visual login specification remains a draft.

## Structure
- docs/: project state, rules, development guidance and feature specifications
- bin/: repository checks and the Windows entry point
- .docker/: development container image configuration
- compose.yaml: development app service; run Compose from the repository root
- src/: older draft Compose configuration; no application source yet

## Non-standard
- Run Node and Yarn only in the app container, through `docker compose exec app`.

## Where to look
- docs/state.md: first, in every session
- docs/hard-rules.md: before you change any file
- docs/dev-environment.md: how to start the project
- docs/testing.md: before you say something works
- docs/architecture.md: before you add a module or change how parts connect
- docs/conventions.md: before you write code or commit
- docs/workflow.md: before you open a pull request or release
- docs/decisions.md: before you reopen a decision
- docs/specs/: the spec, before you build anything
- docs/ai-log.md: the human's own AI log; read it, never edit it
- .agents/skills/: procedures, one folder each; read the description at the top of each SKILL.md and follow the one that matches the task
