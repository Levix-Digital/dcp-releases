# Dev Cycle Protocol releases

**The engineering process for your coding agents.**

The agent writes the code. Dev Cycle Protocol makes sure it was done the right way: specification, plan, tests, review and release, with no steps skipped.

This repository publishes the releases of Dev Cycle Protocol. It holds no source code: every version is under [Releases](https://github.com/Levix-Digital/dcp-releases/releases).

## Requirements

- Git
- A coding agent that reads `SKILL.md` skills (Claude Code, Codex, Gemini, Copilot or similar)
- Network access to GitHub on the first run of each version (the launcher downloads the engine binary). No Python is needed.

## Install

1. Download the install package of the latest release and extract it to `~/.ai-code-agent-skills`.

   macOS / Linux:
   ```bash
   mkdir -p ~/.ai-code-agent-skills
   curl -fsSL https://github.com/Levix-Digital/dcp-releases/releases/latest/download/dev-cycle-protocol.tar.gz \
     | tar -xz --strip-components=1 -C ~/.ai-code-agent-skills
   ```

   Windows: download [`dev-cycle-protocol.zip`](https://github.com/Levix-Digital/dcp-releases/releases/latest/download/dev-cycle-protocol.zip) and extract the folder inside it to `$HOME\.ai-code-agent-skills`.

2. Link the skills into your agents.

   macOS / Linux:
   ```bash
   ~/.ai-code-agent-skills/install.sh
   ```

   Windows:
   ```powershell
   & "$HOME\.ai-code-agent-skills\install.ps1"
   ```

3. Restart the agent (or open a new session) so it picks up the skills.

4. In a project, type `/dev-cycle` in your agent. Agents without slash commands: say "start the dev cycle".

The package carries the full user guide (`README.md` and `docs/`): other agents and install options, cloud sessions, project configuration and troubleshooting.

## Update

Repeat step 1 with the new release, then run the install script again.

## A specific version

Replace `latest/download` with `download/<tag>` in the links above, for example `download/v2.10.0`. Release candidates (`vX.Y.Z-rc.N`) are never the latest release; install one this way to test it.

## What a release contains

| Release | Contents |
|---|---|
| `vX.Y.Z` (product) | `dev-cycle-protocol.tar.gz` and `dev-cycle-protocol.zip`: the skills, the launchers, the installers and the user guide; `SHA256SUMS` |
| `engine-vX.Y.Z` (engine) | One `dev-cycle` binary per platform (Linux, macOS, Windows; x86_64 and aarch64) and `SHA256SUMS` |

You do not download the engine yourself. The launcher in the package downloads the binary of the engine version it needs on first use and checks it against `SHA256SUMS`.

## License

Copyright (c) 2026 Levix Digital. All rights reserved.

Dev Cycle Protocol is proprietary software. Its use is subject to the terms in the `LICENSE` file of each install package. Versions published under the MIT License or the Apache License, Version 2.0 (up to engine version 0.46.1 and release candidate v2.10.0-rc.1) stay available under those licenses.
