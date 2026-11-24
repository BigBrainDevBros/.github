# Contributing to BigBrainDevBros

Welcome to **BigBrainDevBros**! This document defines the shared collaboration, coding, and commit standards across organization repositories.

## Access & Permissions

- All organization members have **Write** access by default across repositories.
- Maintainers and members may push directly to `main` on repositories that follow trunk-based development, or open pull requests for larger or cross-cutting changes.
- **Never force-push or delete `main`.**

## Commit Message Convention

Most repositories enforce a concise 3-word conventional commit format in CI:

```text
type: word word word
```

- Matches `^[a-z]+: [a-z0-9]+ [a-z0-9]+ [a-z0-9]+$`
- Allowed types: `feat`, `fix`, `docs`, `ci`, `chore`, `refactor`, `test`, `perf`, `style`
- No scopes, no parentheses, no trailing punctuation (e.g., `feat: add hub navigation`, `fix: guard break timing`).

## Before Pushing or Opening a PR

1. Run the repository's build and test checks (e.g., `npm run build`, `python3 tools/build.py --check`, `node tools/tests/test.mjs`, or `unittest`).
2. Keep tracked filenames lowercase where enforced by repository CI.
3. Verify no secrets, tokens, or local build/log artifacts are staged.
4. Update documentation or changelogs when changing user-facing behavior or deployment requirements.
