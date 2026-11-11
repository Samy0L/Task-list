# Workflow

Read this before preparing a pull request or release. The repository
currently contains documentation, agent guidance and partial tooling
configuration; it has no application code.

## For each task

1. Read docs/state.md, the relevant project guides, and any existing feature
   spec. Ask about missing requirements that affect the work.
2. Write or update the feature spec in docs/specs/, using
   docs/specs/TEMPLATE.md. Keep unresolved choices explicit.
3. Explain the implementation plan before writing application code. Work
   within the agreed scope and ask before adding dependencies.
4. Review the diff and follow docs/testing.md. Run bin/check, or
   bin\check.cmd on Windows. When application code exists, run its checks
   and try the affected behavior by hand.
5. Update docs/state.md with remaining work and questions. Record agreed
   decisions in docs/decisions.md when they need to be remembered.
6. The human writes their own account in docs/ai-log.md. The agent never
   edits that file.
7. Review the changes before committing. Pushing and opening a pull request
   depend on the collaboration process agreed for the task. An `origin`
   remote and local `main` branch exist; a required pull request process
   has not been agreed.

## Releases

There is no release or deployment process yet. Choose a target environment
and document the release steps when deployment becomes part of the work.
