# Architecture

Read this before adding a module or changing how parts connect.

## Current repository

The repository contains agent instructions, project documentation, feature
specification templates, and the configuration check in bin/. There is no
application code, server, database, or implemented authentication yet.

Partial tooling configuration also exists: root package-manager declarations,
a container image declaration in `.docker/`, and a draft Compose service in
`src/`. These do not yet form a verified application setup. See
docs/dev-environment.md for their declarations and current path mismatches.

The agreed frontend direction is Vue + Vite + TypeScript, with Tailwind CSS
for styling. This is a technology choice, not an installed or configured stack.
The owner will create the application setup later.

## Planned responsibilities

- Accounts: support people using their own accounts.
- Tasks: provide the application's to-do functionality.
- Administration: provide administrative functionality; its operations and
  permissions still need to be defined.
- Login page: the first feature to specify, styled with Tailwind. Today's work
  is its draft specification in docs/specs/. The planned first version is a
  Romanian visual demo with a dark theme and local form validation.

These are product responsibilities, not an agreed folder structure or a
decision to use separate services.

## Connections

The planned login demo validates input locally and displays a message that
authentication is not connected. It does not call an authentication API or
create an authenticated session. No backend work is part of the current task.

The future backend, API endpoints, request formats, redirect destinations and
authentication provider remain undecided. Record those choices here and in the
relevant spec when they are agreed.

## Data

No application data is stored yet. The database, account and task schemas,
session handling, and rules for reading or changing data remain undecided.
Do not infer administrative access or task ownership rules from the product
name alone.

## Related documents

Use docs/dev-environment.md for startup instructions, docs/decisions.md for
agreed choices and their reasons, and docs/specs/ for feature behavior.
