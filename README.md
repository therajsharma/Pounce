# Pounce

[![Tests](https://github.com/therajsharma/Pounce/actions/workflows/test.yml/badge.svg)](https://github.com/therajsharma/Pounce/actions/workflows/test.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python 3.13](https://img.shields.io/badge/python-3.13-blue.svg)](https://www.python.org/downloads/)

Pounce is a Codex-native dependency security layer that vets exact package releases, enforces shell-time install guardrails, blocks unexplained manifest edits, and surfaces trust state directly in chat.

![Pounce plugin overview](docs/git_main.png)

## Quick start

Add the GitHub-backed Pounce marketplace to Codex:

```bash
codex plugin marketplace add therajsharma/Pounce --ref main
```

Then install and enable the plugin inside Codex:

1. Open or restart Codex.
2. Run `/plugins`.
3. Choose `Local Security Plugins`.
4. Install `Pounce`.
5. Open a Codex session in the repository you want protected.

On the first prompt in that repository, Pounce bootstraps the workspace automatically. It writes:

- `AGENTS.md` with the managed Pounce policy
- `.codex/hooks.json` with the Pounce `UserPromptSubmit`, `PreToolUse`, and `Stop` hooks
- `.codex/config.toml` with `codex_hooks = true`

Users who install through the Codex Marketplace do not need to clone this repository or run `install_local.py`.

Ask Codex to confirm the install:

```text
Show the Pounce dashboard for this workspace
```

A fully bootstrapped workspace reports `Protection status: protected`.

For a stable team rollout, publish a release tag and install that tag instead of `main`:

```bash
codex plugin marketplace add therajsharma/Pounce --ref v0.1.0
```

## Local development

For local development from this repository:

```bash
python3 plugins/pounce/scripts/install_local.py --workspace "$(pwd)"
python3 plugins/pounce/scripts/pounce_demo.py
pytest -q
```

## What it protects

- Exact release vetting for npm and PyPI through `pounce.vet`
- Same-turn hook enforcement for risky dependency installs
- Dependency guard snapshots for manifests and lockfiles
- Workspace sweeps for malicious indicators and install-time mechanisms
- Feed trust reporting with bounded hosted-feed transport

## Security posture

- Hosted feeds are HTTPS-only, redirects are disabled, and responses are capped at 5 MiB.
- `pounce.vet` stays usable when verification is degraded, but now returns `verification_status` and `manual_review_required`.
- Hook-enforced dependency installs fail closed when verification is unavailable, throttled past the bounded retry window, or the guard state is missing or corrupt.
- Package names are validated before subprocess or registry use, and the `npm view` path uses an explicit `--` separator.
- Workspace writes are confined so stamps, guard state, and installer output cannot target `/`, `$HOME`, plugin internals, or shared state directories.

## Repository layout

- `plugins/pounce/scripts/pounce_runtime.py`: release vetting, guard state, dashboard assembly, command analysis
- `plugins/pounce/scripts/pounce_intel.py`: feed normalization, sync, hosted-feed loading, source precedence
- `plugins/pounce/scripts/pounce_mcp_server.py`: MCP surface, request validation, sanitized error handling
- `plugins/pounce/scripts/pounce_hook.py`: hook enforcement entrypoint

## Verification

- `python3 plugins/pounce/scripts/pounce_demo.py --json`
- `python3 -m pytest -q`

## Docs

- [Plugin README](plugins/pounce/README.md)
- [Getting started guide](docs/getting-started.md)
- [Final spec](docs/pounce-final-spec.md)
