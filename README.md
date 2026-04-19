# Skylence

**Claude Code harness builder.** Listens for GitHub webhook events, matches them to workflow definitions, and runs each step by calling the `claude` CLI — streaming results over WebSocket in real time.

- No account. No cloud. State stored locally in SQLite.
- Workflows are `.sky` files in your repository, authored by an LLM, reviewed by a human.
- Per-node and monthly spend caps enforced before Claude is invoked.
- `sky lint` catches injection risks and schema errors before any workflow runs.

**→ [docs.skylence.be](https://docs.skylence.be)** — full documentation

---

## Installation

One command. Auto-detects OS and architecture, verifies checksum, installs to `/usr/local/bin/sky`.

```sh
curl -fsSL https://github.com/skylence-be/skylence/releases/latest/download/install.sh | sh
```

Then:

```sh
sky --version
sky setup
```

macOS and Linux on amd64 and arm64. Windows not supported (use WSL2).

### Self-update

```sh
sky update          # install latest release
sky update --check  # check without installing
```

### Manual install

Download archives and checksums from [Releases](https://github.com/skylence-be/skylence/releases).

---

## Quick start

```sh
sky setup                                                          # init ~/.sky/, check deps
sky serve                                                          # start daemon on :3090
sky webhook register --repo owner/name --url https://your-tunnel  # register GitHub webhook
sky lint                                                           # validate .sky workflows
sky run <workflow> --repo /path/to/repo --issue 42                # run manually
sky logs                                                           # view results
```

Full walkthrough: [docs.skylence.be/getting-started](https://docs.skylence.be/getting-started/)

---

## Source

The source code is private. This repository hosts public release artifacts only.

- [Report a bug](https://github.com/skylence-be/skylence/issues/new?template=bug.yml)
- [Request a feature](https://github.com/skylence-be/skylence/issues/new?template=feature.yml)
- [Ask a question](https://github.com/skylence-be/skylence/discussions)
- [Security policy](SECURITY.md)
