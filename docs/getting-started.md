# Getting Started with Pounce

Pounce adds dependency vetting, shell-time install guardrails, workspace sweeps, and chat-native protection visibility to Codex.

## Quick path

1. Add the Pounce marketplace to Codex.
2. Install Pounce from `/plugins`.
3. Open the dashboard in Codex chat.

## Install from GitHub

Add the Pounce marketplace directly from GitHub:

```bash
codex plugin marketplace add therajsharma/Pounce --ref main
```

Open a new Codex session, then run:

```text
/plugins
```

Choose `Local Security Plugins`, search for `Pounce`, and install it. For a stable team rollout, publish a release tag and use that tag instead of `main`:

```bash
codex plugin marketplace add therajsharma/Pounce --ref v0.1.0
```

After Pounce is installed and enabled, open or restart a Codex session in the target repository. The first Pounce hook invocation bootstraps that workspace by writing:

- `AGENTS.md` with the managed Pounce policy block
- `.codex/hooks.json` with the Pounce `UserPromptSubmit`, `PreToolUse`, and `Stop` hooks
- `.codex/config.toml` with `codex_hooks = true`

This is the Marketplace path for teammates. They do not need a local Pounce checkout or the development installer.

### If the marketplace command fails with `ENOENT`

If `codex plugin marketplace add ...` fails while trying to spawn a missing path under `node_modules/@openai/codex-darwin-arm64`, the local Codex CLI install is incomplete. Repair Codex first, then rerun the marketplace command:

```bash
npm uninstall -g @openai/codex
npm install -g @openai/codex@0.130.0
codex plugin marketplace add therajsharma/Pounce --ref main
```

## Local development install

If you are developing Pounce from a local checkout, run this from the repository root:

```bash
python3 plugins/pounce/scripts/install_local.py --workspace "$(pwd)"
```

## Smoke demo

Run the deterministic smoke check:

```bash
python3 plugins/pounce/scripts/pounce_demo.py
```

Optional JSON output:

```bash
python3 plugins/pounce/scripts/pounce_demo.py --json
```

## Use it in Codex

After installation, ask Codex:

```text
Show the Pounce dashboard for this workspace
```

The dashboard summarizes workspace protection, feed trust state, and recent vet or sweep results.

## Run verification

Run the test suite from the repository root:

```bash
pytest -q
```

## Optional feed refresh

If network access is available, refresh the local intelligence feeds:

```bash
python3 plugins/pounce/scripts/pounce_feed.py sync
```

## Limited-network behavior

Pounce keeps the core workflow usable even when feed refresh is skipped. The dashboard falls back through remote cache, local sync cache, and bundled seed data, while hosted feeds stay bounded to HTTPS, no redirects, and a 5 MiB response cap.
