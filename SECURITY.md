# Security Policy

## Supported Versions

Only the latest release and the `main` branch of each active **BigBrainDevBros** repository receive security updates.

## Reporting a Vulnerability

If you discover a security vulnerability, credential exposure, or abuse vector in any **BigBrainDevBros** repository, please do **not** open a public GitHub issue.

Instead, report it privately via **GitHub Security Advisories** on the affected repository:

`https://github.com/BigBrainDevBros/<repository>/security/advisories/new`

Please include:

- The affected repository, branch/tag, and file path(s).
- Clear reproduction steps or a minimal proof of concept.
- Potential impact and any suggested remediation.

We will acknowledge receipt promptly and coordinate a fix before public disclosure.

## Organization Security Standards

- Never commit API tokens, private keys, Worker secrets, database dumps, or personal email addresses.
- Keep GitHub Actions workflows scoped to least-privilege `permissions` (default `contents: read`).
- Review Dependabot alerts and automated security updates promptly.
- Never force-push or rewrite history on `main`.
