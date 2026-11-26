# Contributing To BigBrainDevBros

[简体中文](contributing.zh-cn.md) · [Workspace Templates](template.md) · [Policy Guidelines](check.md) · [Security Policy](security.md)

All contributors and AI agents working in **BigBrainDevBros** repositories must strictly comply with the mandatory organization standards defined in [Policy Guidelines](check.md) and [Workspace Templates](template.md).

## Access And Permissions

- All organization members have **Write** access by default across repositories.
- Maintainers and members may commit directly to `main` on repositories that follow trunk-based development, or open pull requests for cross-cutting changes.
- Never force-push, rewrite history on, or delete `main`.

## Mandatory Standards Summary

1. **No Direct Binary Links**: Route all binaries exclusively through GitHub Releases or package managers (`brew install`).
2. **Strict Commit Messages**: Match `^[a-z]+: [a-z0-9]+ [a-z0-9]+ [a-z0-9]+$` (prefix + space + exactly three lowercase words).
3. **Lowercase Paths**: Keep all tracked files and directories strictly lowercase (except explicitly permitted repository exceptions such as `TornTools`).
4. **Title Case Headers And No Emojis**: Format all Markdown headers in Title Case and use plain text instead of emojis in documentation and templates.
5. **No Unapproved Releases**: Never tag, release, or publish packages without explicit maintainer approval.

## Bilingual Documentation Checks

The read-only `bilingual-docs.yml` reusable workflow checks reciprocal English and Simplified Chinese navigation for README, contributing and wiki home pages. Call it from a repository workflow using `jobs.<job>.uses` with the reviewed commit SHA of `BigBrainDevBros/.github/.github/workflows/bilingual-docs.yml`. Reviewers still check translations and release numbers.
