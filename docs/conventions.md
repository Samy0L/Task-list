# Conventions

How code is written and committed here. Read this before writing code or
making a commit.

## Language

Code, comments, commit messages and the files in docs/ are written in English.
The first login demo uses Romanian interface text. Its labels and messages are
recorded in docs/specs/login.md; the specification itself remains in English.

## Code style

- Follow .editorconfig: UTF-8, LF line endings, two spaces for indentation,
  a final newline, and no trailing whitespace. Windows .cmd files use CRLF.
- The planned frontend uses Vue and TypeScript. No formatter or linter is
  configured yet; select tooling during the owner's future setup and ask
  before adding dependencies.
- Use descriptive names and keep changes focused on the agreed feature.
- Describe future functionality as planned until it has been implemented
  and checked.

## Branches

There is no project-specific branch policy yet. When a task uses a separate
branch, use a short descriptive name such as feature/login-page or
docs/project-setup. Do not rename an existing branch as part of unrelated work.

## Commit messages

Default to a short English imperative subject under 72 characters, such as
"Document Task List login requirements". Add a body when the reason for a
change needs explanation. Keep unrelated changes in separate commits.
