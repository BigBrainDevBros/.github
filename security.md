# Security Policy

## Supported Versions

Only the latest release and the `main` branch of each active **BigBrainDevBros** repository receive security updates and compatibility patches.

| Version | Supported |
| :--- | :--- |
| Latest Release | Yes |
| Older Releases | No |

## Reporting A Vulnerability

If you discover a security vulnerability or unintended data exposure in any **BigBrainDevBros** repository, please do **not** open a public issue.

Instead, report it privately through one of the following channels:

- **GitHub Security Advisories**: Open a private security advisory on `https://github.com/BigBrainDevBros/<Repo>/security/advisories/new`.
- **Direct Email**: Contact `evengao6688@gmail.com` with reproduction steps, affected environment details, and impact summary.

## Organization Security Standards

- Never embed direct binary or executable download links (`.dmg`, `.pkg`, `.zip`, `.exe`, `.tar.gz`) in READMEs or Markdown files; route downloads exclusively through GitHub Releases or package managers.
- Never commit API tokens, private keys, Worker secrets, database dumps, or temporary build artifacts.
- Keep GitHub Actions workflows scoped to least-privilege `permissions` (default `contents: read`).
- Never force-push or rewrite history on `main`.
