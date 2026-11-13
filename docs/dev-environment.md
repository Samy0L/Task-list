# Development environment

## Current setup

The development environment runs in the Docker Compose `app` service. Use the
root `compose.yaml` for all commands below, from the repository root. The older
`src/compose.yaml` is not the development entry point.

The agreed frontend direction is Vue + Vite + TypeScript + Tailwind CSS.
Application source and development/build scripts have not been added yet:
`package.json` currently contains only `packageManager: yarn@4.18.1`.

## Requirements

- Git; on Windows, Git for Windows supplies the shell used by the check script.
- Docker Engine with Docker Compose v2, with the Docker daemon running. On
  Windows, install and start Docker Desktop in Linux-container mode.
- A text editor that supports UTF-8 and the repository's `.editorconfig`.

Node and Yarn run only inside the `app` container, through
`docker compose exec app`. They do not need to be installed on the host.

## Container configuration

- `.docker/Dockerfile` uses `node:24.22.1-alpine3.24` and enables Yarn through
  Corepack. `package.json` selects Yarn 4.18.1.
- `.yarnrc.yml` selects the `node-modules` linker.
- Root `compose.yaml` builds from `.docker/`, mounts the repository at `/app`,
  sets `/app` as the working directory and runs as user `1000:1000`.
- The service maps host port 5173 to container port 5173 and enables file
  polling with `CHOKIDAR_USEPOLLING` and `CHOKIDAR_INTERVAL`.

On 2026-11-13, the existing `app` container was running, and version commands
inside it returned Node v24.22.1 and Yarn 4.18.1.

## Start and stop

Build the development image and start the container in the background:

```sh
docker compose up -d --build app
```

Check the container's status:

```sh
docker compose ps
```

Stop the container:

```sh
docker compose stop app
```

Run the start command again to resume development. To stop and remove the
Compose containers and network instead:

```sh
docker compose down
```

Once a development server is running, its local address will be
`http://localhost:5173`. The current Compose file starts the Node container
without a web-server command; no development server was running when inspected.
A future server must listen on `0.0.0.0:5173` inside the container for that
address to serve the application. There is no `dev` script to run yet.

## Run a Yarn command

Start `app` first, then put the Yarn command after `docker compose exec app`:

```sh
docker compose exec app yarn --version
```

For example, dependency installation and a project build use:

```sh
docker compose exec app yarn install
docker compose exec app yarn build
```

The build command requires a `build` script in `package.json`, which is currently
missing. Do not run Node or Yarn commands directly on the host. For automated
checks, add `-T` to disable terminal allocation:

```sh
docker compose exec -T app yarn build
```

## Check the repository

From the repository root in PowerShell or Command Prompt:

```powershell
bin\check.cmd
```

From the repository root on macOS, Linux or Git Bash:

```sh
sh bin/check
```

Start `app` before running the check. It validates repository guidance and runs
`docker compose exec -T app yarn build` in its Project section. It reports a
failure if Docker is unavailable, the service is stopped or the build fails.
On 2026-11-13, the repository-guidance checks passed with the existing
`docs/ai-log.md` placeholder warning, but the Project check failed: Yarn reported
that the workspace was not present in its lockfile. A `build` script is also
still missing from `package.json`. The check does not start a development server
or check browser behavior.

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
