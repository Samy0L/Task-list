# Development environment

## Current stage

Task List currently contains repository guidance and feature specifications.
There is no application code, database or development server yet. Partial tooling
configuration exists, as listed below. The agreed frontend direction is
Vue + Vite + TypeScript + Tailwind CSS. The owner confirmed that the current task
is documentation and a draft visual login specification. Application setup
remains with the owner.

## Requirements

- Git; on Windows, Git for Windows supplies the shell used by the check script.
- A text editor that supports UTF-8 and the repository's `.editorconfig`.

## Existing setup declarations

- Root `package.json` declares `packageManager: yarn@4.18.1`; it has no
  application dependencies or scripts.
- Root `.yarnrc.yml` declares `nodeLinker: node-modules`.
- `.docker/Dockerfile` declares the base image `node:24.22.1-alpine3.24` and
  runs `corepack enable yarn`.
- `src/compose.yaml` declares an `app` service with port mapping `5173:5173`,
  a working directory of `/app` and a source bind mount.

These are declarations found in the repository, not verified installations or
a working development environment. No image build, dependency installation or
application startup was performed for this documentation task. Confirm the
intended setup with the owner before installing dependencies or changing it.

## Check the repository

From the repository root in PowerShell or Command Prompt:

```powershell
bin\check.cmd
```

From the repository root on macOS, Linux or Git Bash:

```sh
sh bin/check
```

The command checks repository guidance; it does not start a web application.

## Start and stop the application

No verified application start or stop command or local URL exists yet. The
Compose port mapping alone does not establish a running Vite server.

The draft Compose file needs attention during setup:

- Its `build: .docker` resolves relative to `src/compose.yaml`, to `src/.docker`;
  the existing Dockerfile is instead in the root `.docker/` directory.
- Its `.:/app` bind mount refers to `src/`, excluding the root `package.json`
  and `.yarnrc.yml`.
- It does not define a development-server command; `package.json` has no scripts.

When the first implementation is added, record the installation command, start
command, local URL and stop procedure here, after actually verifying them.

## Common problems

### Windows resolves `sort` to the Windows utility

Observed on 2026-11-11: `bin\check.cmd` printed
`-uThe system cannot find the file specified.` while still reporting green.
The document-path check uses Unix `sort -u`, but Windows found its own
`sort.exe` first. Treat that run as incomplete.

On this machine `sh` is Git for Windows' shell. Put its tools directory first
in the current PowerShell session, then rerun the check:

```powershell
$gitShellDirectory = Split-Path -Parent (Get-Command sh -CommandType Application).Source
$env:PATH = "$gitShellDirectory;$env:PATH"
.\bin\check.cmd
```

This changes PATH for the current terminal only. The rerun must have no `sort`
error and must print the result of the document-path check.
