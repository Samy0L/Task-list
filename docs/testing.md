# Testing

Read this before reporting that a change works.

## Repository check

From the repository root on Windows:

```powershell
bin\check.cmd
```

On macOS, Linux or Git Bash:

```sh
sh bin/check
```

This checks the length and completeness of `AGENTS.md`, its document index,
and the pointer files for other agents. It warns about unfinished document
placeholders. The placeholder in the human-owned `docs/ai-log.md` must be
reported as a warning, not removed by an agent. Also inspect the Gemini pointer,
because the script only checks its presence indirectly when the file exists.

On Windows, a green summary accompanied by a `sort` error is incomplete. Use
the PATH workaround in `docs/dev-environment.md` and rerun the check.

For documentation changes, read the diff, verify that referenced paths exist
and that commands match the current repository, then run the repository check.
The check does not validate application behavior.

## Application checks

There is no application code, linter or automated test suite yet, so commands
for all tests or an individual test do not exist. Choose suitable checks with
the first implementation and add them to the project-check section of
`bin/check`. Document their exact commands here.

For the login page, manually try each acceptance behavior in its specification
in a browser after implementation. The current draft covers a Romanian dark
theme, username and password, required-field errors, demo submission feedback,
keyboard use and 320 px / 1280 px viewport widths. Review Tailwind usage in the
source separately; appearance alone cannot establish which styling tool is used.
Record the browser and actual results; unchecked items in a draft spec are not
passing tests.

## Reporting

- Report documentation validation separately from application validation.
- Report a feature as done only after its agreed behaviors have been tried
  manually and the repository and applicable application checks pass.
- Report a failing test rather than deleting it or changing it to obtain green.
