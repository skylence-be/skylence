# Security Policy

## Supported versions

Only the latest release of Skylence receives security fixes. Upgrade to the latest version before reporting a vulnerability.

```sh
sky update --check   # check if a newer version is available
sky update           # install the latest release
```

## Reporting a vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Report security bugs privately via [GitHub Security Advisories](https://github.com/skylence-be/skylence/security/advisories/new). You will receive a response within 72 hours.

Please include:

- A description of the vulnerability and its impact
- Steps to reproduce or a proof of concept
- The `sky --version` output and your OS/platform
- Any relevant error codes (`SKY-XX-NNN`) or log output

## Scope

In scope:

- Authentication bypass or privilege escalation in the daemon
- Command injection via webhook payloads, workflow files, or template variables
- SSRF, DNS rebinding, or request forgery through http nodes
- HMAC bypass on webhook ingress
- Unsafe deserialization or path traversal in `.sky` file parsing

Out of scope:

- Vulnerabilities requiring physical access to the machine running `sky`
- Issues in the `claude` CLI binary itself (report those to Anthropic)
- Denial of service via resource exhaustion without meaningful security impact

## Disclosure

Once a fix is released, the vulnerability will be disclosed via a GitHub Security Advisory and noted in the release notes.
