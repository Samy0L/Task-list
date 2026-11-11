# State

Updated: 2026-11-11. Read this first in every session.

Task List is planned to have accounts, tasks and administration. The frontend
direction is Vue + Vite + TypeScript + Tailwind CSS. The owner reconfirmed
documentation and a draft login specification only, with application setup left
to the owner. No application code exists.

Partial tooling declarations exist in package.json, .yarnrc.yml, .docker/ and
src/compose.yaml. Their setup is unverified; Compose path mismatches and missing
startup configuration are documented in docs/dev-environment.md.

The repository guidance and agent pointers are completed. The repository check
passes with the human-owned AI log's placeholder warning; the observed Windows
PATH workaround is documented in docs/dev-environment.md.
A fresh agent without chat history found the startup guide through AGENTS.md
and confirmed that no verified application startup is available yet.

## In progress

- The login specification is a draft: a Romanian visual demo with a dark theme,
  username and password, required fields, validation messages after submission
  and feedback that authentication is not connected. The owner's review of
  the proposed exact text and layout is next, before planning implementation.
- Next setup step belongs to the owner: configure the frontend and record the
  actual versions, installation/start commands and verification tools.

## Open questions

- Owner, next: approve or revise the draft login specification's exact text,
  layout and acceptance behaviors.
- Owner, before backend implementation: backend stack, data storage and sessions.
- Owner, before later feature specs: what may administrators manage, and who
  can view or change each user's tasks?

## Rejected proposals

None recorded.
