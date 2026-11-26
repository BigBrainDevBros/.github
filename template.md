# Canonical Workspace Template Specifications

This document defines the official, standardized templates and structural conventions for all software projects located within `/Users/even/Desktop/Projects`. It operates as the canonical companion to `check.md`, providing concrete templates, badge standards, release formats, and syntax rules for every repository archetype.

---

## 1. File And Directory Naming Taxonomy

Every file and directory tracked in Git must strictly use **lowercase naming** with hyphen (`-`) or underscore (`_`) separators. CamelCase or capitalized directory/file names in Git trees are prohibited to ensure cross-platform case-sensitivity compatibility across macOS, Linux, and FreeBSD.

### General File Classification Rules

| Category | Naming Pattern | Permitted Extensions | Concrete Examples |
| :--- | :--- | :--- | :--- |
| **Swift Sources** | `[domain][entity].swift` | `.swift` | `appupdatechecker.swift`, `discoveryview.swift` |
| **TypeScript / Web** | `[module-name].ts` | `.ts`, `.tsx`, `.js` | `sim-adapter.ts`, `telemetry-bus.ts`, `main.ts` |
| **Python Sources** | `[module_name].py` | `.py` | `forensic_engine.py`, `brief_builder.py`, `__init__.py` |
| **Shell Scripts** | `[action]-[target].sh` | `.sh` or none | `build-dmg.sh`, `verify-release.sh`, `brewstore` |
| **Primary Docs** | `[topic].md` | `.md` | `readme.md`, `changelog.md`, `check.md`, `template.md`, `security.md` |
| **Localized Readmes** | `readme.[lang].md` | `.md` | `readme.de.md`, `readme.es.md`, `readme.fr.md`, `readme.ja.md`, `readme.zh-cn.md`, `readme.zh-tw.md` |
| **CI Workflows** | `[workflow].yml` | `.yml`, `.yaml` | `ci.yml`, `quality.yml`, `release.yml` |
| **Xcode Assets** | `[name].[set]/contents.json` | `.json` | `appicon.appiconset/contents.json` |
| **Homebrew Packaging** | `[formula-or-cask].rb` | `.rb` | `casks/brewstore.rb`, `formula/brewstore.rb` |
| **License File** | `license` | None | `license` |

### Strict No-Emoji Policy

- **Zero Emojis**: Do not use Unicode emojis or GitHub emoji shortcodes (`:white_check_mark:`, `:x:`, `:rocket:`, etc.) in any `readme.md`, `changelog.md`, `security.md`, release description, `.github/` template, or specification document.
- **Plain-Text Status Values**: Use clear text values (`Yes` / `No`, `Supported` / `Unsupported`, `Pass` / `Fail`, `Valid` / `Invalid`) in tables and checklists.

### Repository-Specific Exceptions

- **`Extensions/TornTools`**: Does **not** follow `check.md` or `template.md`. It strictly adheres to upstream creator conventions (`Mephiles/torntools_extension`), including standard uppercase documentation filenames (`README.md`, `CONTRIBUTING.md`, `LICENSE.md`, `FIREFOX.md`), 4-space tab indentation, Oxfmt/Oxlint formatting and linting, and atomic feature commits.

---

## 2. Repository README Templates

Every project repository must provide a clean, scannable `readme.md` modeled on the `GeoFS_Extension` layout: centered hero header, concise badge row, single-line dot-separated navigation bar, and focused content sections with zero emojis.

### Universal README Structure

1. **Centered Hero (`<div align="center">`)**:
   - `# Project Name` (clean text, no emoji)
   - One-line bold subtitle / pitch
   - 3 to 5 `flat-square` Shields.io badges
   - Single-line dot-separated navigation bar: `[Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)` (include `[Roadmap](roadmap.md)` or `[Language](readme.zh-cn.md)` only if those files exist)
2. **Optional Notice Callout**: `> [!CAUTION]` for educational/fair-play disclaimers where applicable.
3. **Key Features**: Concise, scannable bullet points.
4. **Usage / Hotkeys / Commands**: Clean tables or code blocks.
5. **Installation / Development And Build**: Reproducible commands without direct binary download links.

> [!NOTE]
> Omit redundant Table of Contents sections and multi-language bars unless a repository actually ships localized `readme.<lang>.md` files or exceeds ~150 lines.

---

### Archetype A: Native macOS Desktop Application

Use for native macOS SwiftUI and AppKit applications (`BrewStore`, `Juicer`, `PathDeck`).

````markdown
<div align="center">

<img src="sources/resources/assets.xcassets/appicon.appiconset/icon_128x128.png" width="128" height="128" alt="AppName Icon" />

# AppName

**Native macOS Companion For Package Management And System Maintenance**

![Platform](https://img.shields.io/badge/Platform-macOS%2014%2B-blue?style=flat-square)
![Swift](https://img.shields.io/badge/Swift-5.10%2B-orange?style=flat-square)
![Release](https://img.shields.io/badge/Release-v1.0.0-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

---

## Key Features

- **Visual Package Storefront**: Search, inspect, install, and safely remove casks and formulas.
- **Preview-First Uninstall Safety**: Review reverse-dependency impact before committing deletions.
- **Granular Storage Cleaner**: Analyze and reclaim orphaned build caches and logs.
- **Local-First Execution**: Zero telemetry, tracking, or background network pings.

---

## Installation

### Via Official Homebrew Tap (Recommended)

```bash
brew tap AMFI-Disable/tapname
brew install --cask appname
```

### Manual Release Installation

Download verified `.dmg` packages from [GitHub Releases](https://github.com/AMFI-Disable/AppName/releases) and verify the SHA-256 checksum:

```bash
shasum -a 256 appname-1.0.0.dmg
```

Because this is an unnotarized open-source build, macOS Gatekeeper quarantines downloaded bundles by default:

```bash
sudo xattr -r -c /Applications/AppName.app
```

Alternatively, open **System Settings > Privacy & Security** and click **Open Anyway**.

---

## Development And Testing

```bash
xcodegen generate
xcodebuild test \
  -project AppName.xcodeproj \
  -scheme AppName \
  -destination "platform=macOS" \
  CODE_SIGNING_ALLOWED=NO
```
````

---

### Archetype B: Python CLI And Terminal Workstation

Use for Python CLI and Textual terminal applications (`OmniSuite`, `Brew-Ghost`).

````markdown
<div align="center">

# AppName

**High-Fidelity Terminal Workstation For System Analysis And Research**

![Platform](https://img.shields.io/badge/Platform-macOS%20%7C%20Linux-blue?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square)
![Release](https://img.shields.io/badge/Release-v1.0.0-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

---

## Key Features

- **Interactive Terminal UI**: Responsive Textual interface with keyboard-driven workflows.
- **Local-First Storage**: Offline-capable SQLite persistence with zero external telemetry.
- **Headless Automation**: Scriptable CLI subcommands for batch processing and CI.

---

## Installation

```bash
pip install appname
```

Or install from source:

```bash
git clone https://github.com/AMFI-Disable/AppName.git
cd AppName
pip install -e .
```

---

## Usage And Testing

```bash
# Launch interactive terminal UI
appname

# Run test suite
pytest tests/ -v --cov=src
```
````

---

### Archetype C: Homebrew Tap Repository

Use for Homebrew Tap repositories (`Homebrew-Tap`, `Homebrew-BrewStore`, `Homebrew-Juicer`).

````markdown
<div align="center">

# Homebrew-TapName

**Official Homebrew Tap Hosting Formulas And Casks By AMFI-Disable**

![Tap](https://img.shields.io/badge/Tap-Active-success?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

---

## Installation

```bash
brew tap AMFI-Disable/tapname
```

Install desired packages:

```bash
brew install --cask appname
brew install cli-tool
```

---

## Upgrading Packages

```bash
brew update
brew upgrade --cask appname
```
````

---

### Archetype D: Manifest V3 Browser Extension

Use for modern TypeScript/Vite/Preact browser extensions (`GeoFS_Extension`, `FMG`).

````markdown
<div align="center">

# ExtensionName

**Manifest V3 Browser Extension For Target Platform**

![Version](https://img.shields.io/badge/Version-v0.2.0-blue?style=flat-square)
![Manifest](https://img.shields.io/badge/Manifest-V3-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Roadmap](roadmap.md) · [Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

> [!CAUTION]
> **Educational And Fair-Play Disclaimer**: `ExtensionName` is an open-source, client-side enhancement suite intended strictly for educational and personal use. Always respect target platform terms of service and access controls.

---

## Key Features

- **Manifest V3 Architecture**: Clean separation between page-world hooks and isolated extension storage.
- **Zero Global Pollution**: Modular lifecycle (`init` / `update` / `destroy`) with leak-free hot-toggling.
- **Persistent Settings**: Synchronized preferences stored locally via `chrome.storage`.

---

## Development And Build

```bash
npm ci
npm run typecheck
npm test
npm run build:unpacked
```

1. Open `chrome://extensions` in Chromium/Chrome.
2. Enable **Developer mode**.
3. Click **Load unpacked** and select the generated unpacked extension folder.
4. For packaged releases, see [GitHub Releases](https://github.com/AMFI-Disable/ExtensionName/releases).
````

---

### Archetype E: Userscripts And Automation

Use for Tampermonkey/Violentmonkey userscripts (`GimSell`, `Lichess-AutoPlayer`, standalone `.user.js` scripts).

````markdown
<div align="center">

# ScriptName

**Automated In-Page Utility And Overlay For Target Platform**

![Platform](https://img.shields.io/badge/Browser-Chrome%20%7C%20Firefox%20%7C%20Safari-blue?style=flat-square)
![Manager](https://img.shields.io/badge/Manager-Tampermonkey%20%7C%20Violentmonkey-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

> [!CAUTION]
> **Educational And Fair-Play Disclaimer**: This codebase is provided strictly for educational, research, and testing purposes in authorized environments. Using automated scripts in violation of platform terms of service may lead to account penalties.

---

## Key Features

- **Contextual Activation**: Initializes exclusively on matching host routes.
- **Collapsible Widget**: Minimizes into an unobtrusive floating control panel.
- **Dynamic DOM Observer**: Handles single-page application (SPA) route changes cleanly.

---

## Keyboard Hotkeys

| Platform | Toggle Panel |
| :--- | :--- |
| **macOS** | `Option + S` |
| **Windows / Linux** | `Alt + S` |

---

## Installation

1. Install [Tampermonkey](https://www.tampermonkey.net/) or [Violentmonkey](https://violentmonkey.github.io/).
2. Create a new userscript, paste the contents of `[script-name].user.js`, and save.
3. Navigate to the target web application to activate the panel.
````

#### Standard UserScript Metadata Header Block

```javascript
// ==UserScript==
// @name         ScriptName - Descriptive Title
// @namespace    https://github.com/AMFI-Disable/[Repo]
// @version      1.0.0
// @description  Concise functional description of the userscript
// @author       AMFI-Disable
// @match        https://*.target-domain.com/*
// @grant        none
// @run-at       document-end
// ==/UserScript==
```

---

### Archetype F: Web Games And Interactive Static Apps

Use for browser-native games and static GitHub Pages applications (`DustIII`, `RenYing`).

````markdown
<div align="center">

# GameName

**Browser-Native Web Game Built With Three.js / Phaser**

![Platform](https://img.shields.io/badge/Platform-Web%20Browser-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

[Play Online](https://amfi-disable.github.io/GameName/) · [Changelog](changelog.md) · [Security Policy](security.md) · [MIT License](license)

</div>

---

## Key Features

- **Zero-Backend Static Build**: Runs directly in modern desktop browsers with zero telemetry.
- **Responsive Controls**: Full keyboard/mouse support and configurable presets.

---

## Development

```bash
npm ci
npm run dev
npm test
```
````

---

## 3. Shields.io Badge Specification

1. **Badge Style**: Always specify `style=flat-square`.
2. **Plain Text Labels**: Use clean Title Case labels and values without emojis (`![Version](...)`, `![License](...)`).
3. **No Direct Binary Links**: Badges must never link directly to `.dmg`, `.zip`, or raw binary files.

---

## 4. Versioning, Milestones, Tags, And GitHub Releases

All repositories follow **Semantic Versioning** (`MAJOR.MINOR.PATCH`, optionally suffixed with `-alpha.N`, `-beta.N`, or `-rc.N` for pre-releases).

| Component | When To Increment | Examples |
| :--- | :--- | :--- |
| **`MAJOR` (`X.0.0`)** | Breaking save/protocol/API changes, major engine rewrites, or incompatible config migrations | Rollback protocol change breaking older clients; D1 schema break |
| **`MINOR` (`0.X.0`)** | Backward-compatible feature additions, new modes/maps/heroes, or substantial UI additions | New game mode, new macOS utility module, new extension feature |
| **`PATCH` (`0.0.X`)** | Bug fixes, CI/dependency fixes, performance tuning, documentation updates, or urgent hotfixes | D1 quota protection, CI race fix, link/copy fixes |

### GitHub Milestones And Tags

- **Milestones**: Represent target release versions (`v<MAJOR>.<MINOR>.<PATCH> — <English Focus> / <中文主题>`, e.g., `v1.1.0 — 20-Hero Depth & Replay 2.0 / 20侠客深度与回放2.0`). All milestone issues must close (or be deferred) before tagging.
- **Git Tags**: Lowercase `v` followed by SemVer (`v1.0.0`, `v1.1.0-rc.1`). Never use `1.0.0`, `V1.0.0`, or `release-1.0.0`.
- **Release Gate**: Tagging and publishing (`vX.Y.Z`) occurs only after milestone criteria are met and CI passes. Urgent patches may release independently on `main`.

### Release Titles And Release Notes Body

| Release Type | Title Formula | Example |
| :--- | :--- | :--- |
| **Feature / Milestone** | `<App Name> v<Version> - <Focus>` | `RenYing v1.1.0 - 20-Hero Depth & Replay 2.0` |
| **Inaugural Release** | `<App Name> v<Version> - Inaugural Release` | `BrewStore v1.0.0 - Inaugural Release` |
| **Maintenance / Patch** | `<App Name> v<Version> - <Fix Focus>` | `BrewStore v1.0.1 - Casing Normalization` |

````markdown
<App Name> v<Version> <1-2 sentence executive summary explaining what this release adds, fixes, or improves.>

### 中文摘要

<可选：重大版本或双语项目的 1-2 句简体中文版本摘要。>

> [!CAUTION]
> **<Optional Contextual Notice Title>**. <Include only when applicable, such as an educational/fair-play disclaimer or an unnotarized macOS build note.>

## Added

- <Concise, user-facing description of new capability or feature.>

## Changed

- <Concise explanation of behavioral change, UI update, or optimization.>

## Fixed

- <Concise explanation of bug fix and what it prevents.>

## Install Or Update

<Tailor this block strictly to how the project is distributed (GitHub Releases Assets, Homebrew cask/formula, or pip).>

[Full Changelog](https://github.com/AMFI-Disable/<Repo>/compare/v<Prev>...v<Curr>)
````

> [!NOTE]
> Omit any `## Added`, `## Changed`, or `## Fixed` section that has no items in the release. Never include placeholder bullets.

---

## 5. Commits, Branches, And Contributor Attribution

All Git commits across managed repositories (excluding `Extensions/TornTools`) must adhere to:

$$\text{type}: \text{word1 } \text{word2 } \text{word3}$$

1. **Type Prefix**: Lowercase prefix followed by `: ` (`feat:`, `fix:`, `docs:`, `ci:`, `chore:`, `refactor:`, `test:`, `perf:`, `style:`).
2. **Word Count & Characters**: **Exactly three words** of lowercase letters and numbers only (`^[a-z]+: [a-z0-9]+ [a-z0-9]+ [a-z0-9]+$`). Optional issue footer: `Refs #N` or `Closes #N`.
3. **No Scopes or Trailing Punctuation**: `feat(ui): add button` and `fix: resolve bug.` are invalid; use `feat: add ui button` and `fix: resolve bug`.
4. **Branch Naming**: Trunk-based `main` (`master` only in `TornTools`). When opening a PR branch, use `<type>/<issue>-<short-slug>` (e.g., `fix/15-mode-sync`, `feat/55-replay-scrub`).
5. **Contributor Attribution**: Never rewrite shared `main` history or strip `Co-authored-by` / original author metadata.

---

## 6. Changelog Specification (`changelog.md`)

Maintain a `changelog.md` following Keep a Changelog with Title Case headers and zero emojis:

````markdown
# Changelog

All notable changes, features, and fixes for this project are documented in this file.

---

## [Unreleased]

### Added

- Brief summary of unreleased feature.

### Changed

- Brief summary of unreleased change.

### Fixed

- Brief summary of unreleased fix.

---

## [1.0.0] - Initial Release

### Added

- **Core Engine**: Initial implementation.
````

---

## 7. Issues, Master Epics, Pull Requests, Discussions, And Projects

### Standardized Issue Title Prefixes

Every new or open issue title must begin with one canonical uppercase bracketed prefix (English or Simplified Chinese allowed after the prefix):

| Prefix | Scope |
| :--- | :--- |
| **`[EPIC]`** | Phased master roadmap coordinating multiple child issues |
| **`[FEATURE]`** | New feature, mode, gameplay mechanic, or enhancement |
| **`[BUG]`** | Defect, regression, or unexpected runtime behavior |
| **`[REFACTOR]`** | Structural code, data, or tooling reorganization |
| **`[PERF]`** | Rendering, simulation, bundle, or quota/latency optimization |
| **`[UI]`** | Visual layout, HUD, accessibility, or audio/UX polish |
| **`[TEST]`** | Automated test suites, regression harnesses, or CI validation |
| **`[DOCS]`** | Documentation, READMEs, wikis, or design specifications |
| **`[SECURITY]`** | Security hardening, permissions, auth, or vulnerability fixes |

### Issue Metadata, Master Epics, And Pull Requests

1. **Labels & Milestones**: Assign priority (`priority: p0`–`p3` or `P0`–`P3`), difficulty (`difficulty: low|medium|high` or `难度: 低|中|高`), `area:*` (`epic` for master epics), target release milestone, and 1 primary assignee (`1–2` concurrent active issues/teammate; no rigid deadlines).
2. **Master Epics**: Declare `Current Version`, `Target Release Version`, `Phased Execution Plan` (`Phase 1..N`), child issue links/dependencies, periodic progress comments citing commit SHAs, and release acceptance criteria.
3. **Pull Requests (`.github/pull_request_template.md`)**: Include bilingual headings (`## Summary / 变更摘要`, `## Linked Issues / 关联议题`, `## Verification Evidence / 验证结果`, `## Checklist / 提交前检查`), passing CI, and peer review on shared core/netplay/server changes.
4. **GitHub Discussions & Projects**: Use `BigBrainDevBros/.github` Discussions (`[Topic] <Summary>` or `[Cross-Repo] <Source> -> <Target>: <Summary>`) for cross-repo ideas; use Project columns `Backlog` -> `Ready` -> `In Progress` -> `In Review` -> `Done` (+ `Paused`).

---

## 8. Bilingual Support Standard (English & Simplified Chinese)

Repositories use a **Three-Tier Bilingual Framework** for English (`en`) and Simplified Chinese (`zh-CN`):

1. **Tier A — English-Only Technical Identifiers**: Commit messages, branch names, SemVer tags, GitHub labels, `[PREFIX]` tags, file/folder paths, code identifiers, and CI workflow/job names remain English.
2. **Tier B — Separate Language Files**: Long-form documentation uses `readme.md` + `readme.zh-cn.md` and `contributing.md` + `contributing.zh-cn.md` with cross-link headers (`[中文文档](readme.zh-cn.md)` / `[English](readme.md)`). `license`, `template.md`, `check.md`, and `changelog.md` stay English as the single canonical specification.
3. **Tier C — Bilingual Shells With Flexible Body Language**: Issue Forms, PR templates, Master Epics, Milestones, Release Notes, and Discussions use bilingual section headers/categories while allowing contributors to write descriptions in either English or Simplified Chinese.

````markdown
## Summary / 变更摘要

Describe what changed and why. / 简述本次改动内容与原因。

## Linked Issues / 关联议题

- Refs #...

## Type Of Change / 变更类型

- [ ] Bug fix (`fix: ...`)
- [ ] New feature (`feat: ...`)
- [ ] Documentation update (`docs: ...`)
- [ ] CI/CD pipeline enhancement (`ci: ...`)
- [ ] Code refactoring (`refactor: ...`)
- [ ] Performance optimization (`perf: ...`)

## Verification Evidence / 验证结果

- Command(s) run and observed results. / 列出执行的测试或构建命令及结果。

## Pre-Flight Verification Checklist / 提交前检查

- [ ] **Strict Commit Message**: Matches `xxx: xxx xxx xxx`
- [ ] **Lowercase Tracked Files**: All added/modified paths are lowercase
- [ ] **Title Case Headers & No Emojis**: Clean Markdown formatting
- [ ] **No Direct Binary Links**: Releases route through GitHub Releases
- [ ] **Bilingual Parity**: `readme.zh-cn.md` updated if `readme.md` changed
- [ ] **Checks And Tests Passed**: Lint, typecheck, and unit tests pass
````

---

## 9. License And Legal Attribution

1. **License File (`license`)**: Lowercase `license` in repository root with `Copyright (c) 2026 AMFI-Disable`.
2. **Reverse-DNS Bundle Identifiers**: `com.amfi-disable.<appname>`.
3. **Application `Info.plist` Copyright String**: `Copyright (c) 2026 AMFI-Disable. Licensed under MIT.`

---

## 10. Standardized Repository `.gitignore` Architecture

Every repository must structure `.gitignore` into two explicit sections:

```gitignore
# ==============================================================================
# SECTION 1: WORKING & PRESERVED FILES (Explicit Whitelists)
# ==============================================================================
!sources/
!src/
!readme*.md
!changelog.md
!security.md
!license
!.gitignore
!.github/

# ==============================================================================
# SECTION 2: HIDDEN & IGNORED ARTIFACTS
# ==============================================================================
# 2.1 System Metadata
.DS_Store
._*
Thumbs.db

# 2.2 IDEs & Editors
.vscode/
.idea/
*.swp
*.swo
*~
*.xcuserdatad/
xcuserdata/
*.xcuserstate

# 2.3 Build Products, Caches & Output Directories
build/
dist/
DerivedData/
.build/
*.pyc
__pycache__/
*.egg-info/
node_modules/

# 2.4 Secrets, Environment Profiles & Diagnostics
.env
.env.*
*.pem
*.key
*.p12
*.log
scratch/
tmp/
.local/
```

### Stack-Specific Whitelist Presets

1. **Native macOS Apps (`Apps/`)**: Whitelist `!project.yml`, `!package.swift`; ignore `*.xcodeproj`, `*.xcworkspace`, `*.dmg`, `.local/build/`.
2. **Python Workstations (`Tools/OmniSuite`, `Science/HiMCM-2026_HEGA`)**: Whitelist `!pyproject.toml`, `!uv.lock`, `!src/`; ignore `.venv/`, `.pytest_cache/`, `.mypy_cache/`, `.ruff_cache/`, `*.db`.
3. **TypeScript / Vite Extensions & Web Games (`Extensions/`, `Games/`)**: Whitelist `!package.json`, `!tsconfig.json`, `!vite.config.ts`, `!vitest.config.ts`, `!public/`; ignore `node_modules/`, `dist/`.
4. **Userscripts (`Extensions/`)**: Whitelist `!*.user.js`; ignore transient bundle artifacts.
5. **Homebrew Taps (`Homebrew/`)**: Whitelist `!Formula/*.rb` or `!formula/*.rb`, `!Casks/*.rb` or `!casks/*.rb`, `!license`, `!readme*.md`.

---

## 11. Documentation Link Integrity, Metadata, And Workflows

1. **Repository-Relative Internal Links**: Always use lowercase relative paths (`[Changelog](changelog.md)`, `[Security Policy](security.md)`, `[License](license)`). Never commit local machine paths (`file:///Users/...`).
2. **Zero Direct Binary Links**: Never embed direct download links to `.dmg`, `.zip`, `.pkg`, `.exe`, or `.tar.gz` in markdown files. Route downloads through GitHub Releases (`https://github.com/AMFI-Disable/<Repo>/releases`) or package managers.
3. **Educational & Fair-Play Disclaimer (`> [!CAUTION]`)**: Required in `readme.md` and release descriptions for automation, scraping, game tools, or simulator extensions.
4. **Repository Metadata**: Every public repository must set a 1-line description, 4–10 lowercase topics, and the live GitHub Pages URL when Pages is enabled.
5. **GitHub Actions Naming**: Use lowercase workflow filenames (`ci.yml` / `CI`, `pages.yml` / `Deploy To GitHub Pages`, `release.yml` / `Release`, `compliance.yml` / `Repository Compliance`) and clear job names (`Preflight & Compliance`, `Build & Unit Tests`, `Deploy Pages`, `Publish Release`).

---

## 12. Security Policy Specification (`security.md`)

Every repository must include a clean, emoji-free `security.md` at the repository root modeled on `GeoFS_Extension/security.md`:

````markdown
# Security Policy

## Supported Versions

Only the latest release of `<ProjectName>` is actively supported with security updates and compatibility patches.

| Version | Supported |
| :--- | :--- |
| Latest Release | Yes |
| Older Releases | No |

## Reporting A Vulnerability

If you discover a security vulnerability or unintended data exposure in `<ProjectName>`, please do **not** open a public issue.

Instead, report it privately through one of the following channels:

- **GitHub Security Advisories**: Open a private security advisory on `https://github.com/AMFI-Disable/<Repo>/security/advisories/new`.
- **Direct Email**: Contact `evengao6688@gmail.com` with reproduction steps, affected environment details, and impact summary.
````
