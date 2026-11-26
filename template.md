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

## 4. Git Tags And Release Versioning

1. **Standard Production Releases**: Lowercase `v` followed by semantic version: `v<MAJOR>.<MINOR>.<PATCH>` (e.g. `v0.2.0`, `v1.0.0`).
2. **Pre-Release Builds**: `v<MAJOR>.<MINOR>.<PATCH>-<stage>.<build>` (e.g. `v1.1.0-rc.1`).
3. **Prohibited Tag Formats**:
   - Invalid: `1.0.0` (missing `v` prefix)
   - Invalid: `V1.0.0` (uppercase `V`)
   - Invalid: `release-1.0.0` or `build-100`

---

## 5. Release Titles And Release Notes Body

The release description template follows the `GeoFS_Extension` format: concise, scannable, emoji-free, with no redundant H1 header, omitting empty change sections, and ending with a GitHub compare link.

### Release Title Standards

| Release Type | Title Formula | Example |
| :--- | :--- | :--- |
| **Feature / Milestone** | `<App Name> v<Version>` or `<App Name> v<Version> - <Focus>` | `GeoFS Extension v0.2.0` |
| **Inaugural Release** | `<App Name> v<Version> - Inaugural Release` | `BrewStore v1.0.0 - Inaugural Release` |
| **Maintenance / Patch** | `<App Name> v<Version> - <Fix Focus>` | `BrewStore v1.0.1 - Casing Normalization` |

### Canonical Release Notes Body Template (`GeoFS_Extension` Standard)

````markdown
<App Name> v<Version> <1-2 sentence executive summary explaining what this release adds, fixes, or improves.>

> [!CAUTION]
> **<Optional Contextual Notice Title>**. <Include only when applicable, such as an educational/fair-play disclaimer for extensions/automation or an unnotarized build note for macOS apps.>

## Added

- <Concise, user-facing description of new capability or feature.>
- <Concise, user-facing description of new capability or feature.>

## Changed

- <Concise explanation of behavioral change, UI update, or optimization.>

## Fixed

- <Concise explanation of bug fix and what it prevents.>

## Install Or Update

<Tailor this block strictly to how the project is distributed:>
- **Browser Extension**: Extract the extension ZIP from **Assets**. Open `chrome://extensions`, enable **Developer mode**, and use **Load unpacked** (or click **Reload** after replacing files).
- **Homebrew / macOS App**: Run `brew update && brew upgrade --cask <cask-name>`, or download `<app-name>-<version>.dmg` from **Assets** and verify its SHA-256 checksum (`<hash>`).
- **CLI / Python**: Run `brew upgrade <formula>` or `pip install --upgrade <package>`.

[Full Changelog](https://github.com/AMFI-Disable/<Repo>/compare/v<Prev>...v<Curr>)
````

> [!NOTE]
> Omit any `## Added`, `## Changed`, or `## Fixed` section that has no items in the release. Never include placeholder bullets.

---

## 6. Commit Message Structure (`xxx: xxx xxx xxx`)

All Git commits across managed repositories (excluding `Extensions/TornTools`) must adhere to:

$$\text{type}: \text{word1 } \text{word2 } \text{word3}$$

1. **Type Prefix**: Lowercase prefix followed by `: ` (`feat:`, `fix:`, `docs:`, `ci:`, `chore:`, `refactor:`, `test:`, `perf:`, `style:`).
2. **Word Count**: **Exactly three words** after the colon and space.
3. **Word Characters**: Lowercase letters and numbers only (`[a-z0-9]`).
4. **Validation Regex**: `^[a-z]+: [a-z0-9]+ [a-z0-9]+ [a-z0-9]+$`
5. **No Scopes or Trailing Punctuation**: `feat(ui): add button` and `fix: resolve bug.` are invalid; use `feat: add ui button` and `fix: resolve bug`.

---

## 7. Changelog Specification (`changelog.md`)

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

## 8. GitHub Issue And Pull Request Templates

Keep `.github/` templates concise, emoji-free, and matched to the repository's actual runtime (do not ask for macOS/Homebrew versions in web games, extensions, or Python tools).

### Bug Report Template (`.github/issue_template/bug_report.md`)

#### Variant 1: Web, Browser Extension, And Script Repositories

````markdown
---
name: Bug Report
about: Report a bug or unexpected behavior
title: "[BUG] "
labels: bug
assignees: AMFI-Disable
---

## Description Of The Defect

A clear and concise description of what the bug is.

## Steps To Reproduce

1. Open '...'
2. Navigate to '...'
3. Trigger '...'
4. Observe the issue.

## Expected Behavior

What you expected to happen.

## Environment Details

- **Project Version**: [e.g. 0.2.0]
- **Browser / Runtime**: [e.g. Chrome 130, Firefox 132, Tampermonkey 5.x]
- **Operating System**: [e.g. macOS 15, Windows 11, Linux]

## Additional Context

Add console errors, screenshots, or reproduction logs here.
````

#### Variant 2: Native macOS Applications And Homebrew Taps

````markdown
---
name: Bug Report
about: Report a bug or unexpected behavior
title: "[BUG] "
labels: bug
assignees: AMFI-Disable
---

## Description Of The Defect

A clear and concise description of what the bug is.

## Steps To Reproduce

1. Launch application or run command.
2. Navigate to '...'
3. Observe error behavior.

## Expected Behavior

What you expected to happen.

## Environment Details

- **App / Formula Version**: [e.g. 1.0.0]
- **macOS Version**: [e.g. Sequoia 15.1]
- **Architecture**: [e.g. Apple Silicon or Intel]
- **Homebrew Version**: [e.g. 4.4.0]

## Additional Context

Add logs or diagnostic details here.
````

#### Variant 3: Python CLI And Research Workstations

````markdown
---
name: Bug Report
about: Report a bug or unexpected behavior
title: "[BUG] "
labels: bug
assignees: AMFI-Disable
---

## Description Of The Defect

A clear and concise description of what the bug is.

## Steps To Reproduce

1. Run command '...'
2. Observe error output.

## Expected Behavior

What you expected to happen.

## Environment Details

- **Tool Version**: [e.g. 1.0.0]
- **Python Version**: [e.g. 3.12]
- **Operating System**: [e.g. macOS 15, Ubuntu 24.04]

## Additional Context

Add tracebacks or logs here.
````

### Pull Request Template (`.github/pull_request_template.md`)

````markdown
## Summary Of Changes

Provide a concise overview of the problem solved and the modifications made.

## Type Of Change

- [ ] Bug fix (`fix: ...`)
- [ ] New feature (`feat: ...`)
- [ ] Documentation update (`docs: ...`)
- [ ] CI/CD pipeline enhancement (`ci: ...`)
- [ ] Code refactoring (`refactor: ...`)
- [ ] Performance optimization (`perf: ...`)

## Pre-Flight Verification Checklist

- [ ] **Strict Commit Message**: Does every commit match `xxx: xxx xxx xxx`?
- [ ] **Lowercase Tracked Files**: Are all added or modified files strictly lowercase?
- [ ] **Title Case Headers**: Are all markdown headings formatted in Title Case?
- [ ] **No Emojis**: Are all modified markdown files and templates free of emojis?
- [ ] **No Direct Binary Links**: Are all markdown files free of direct `.dmg`/`.zip`/`.exe` links?
- [ ] **Checks And Tests Passed**: Have lint, typecheck, and unit tests passed?
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

## 11. Documentation Link Integrity And Policy Compliance

1. **Repository-Relative Internal Links**: Always use lowercase relative paths (`[Changelog](changelog.md)`, `[Security Policy](security.md)`, `[License](license)`). Never commit local machine paths (`file:///Users/...`).
2. **Zero Direct Binary Links**: Never embed direct download links to `.dmg`, `.zip`, `.pkg`, `.exe`, or `.tar.gz` in markdown files. Route downloads through GitHub Releases (`https://github.com/AMFI-Disable/<Repo>/releases`) or package managers.
3. **Educational & Fair-Play Disclaimer (`> [!CAUTION]`)**: Required in `readme.md` and release descriptions for automation, scraping, game tools, or simulator extensions.

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

---

## 13. Versioning And Release Management

All repositories follow **Semantic Versioning** (`MAJOR.MINOR.PATCH`, optionally suffixed with `-alpha.N`, `-beta.N`, or `-rc.N` for pre-releases).

### Increment Rules

| Component | When To Increment | Examples |
| :--- | :--- | :--- |
| **`MAJOR` (`X.0.0`)** | Breaking save/protocol/API changes, major engine rewrites, or incompatible config migrations | Rollback protocol change breaking older clients; D1 schema break |
| **`MINOR` (`0.X.0`)** | Backward-compatible feature additions, new modes/maps/heroes, or substantial UI additions | New game mode, new macOS utility module, new extension feature |
| **`PATCH` (`0.0.X`)** | Bug fixes, CI/dependency fixes, performance tuning, documentation updates, or urgent hotfixes | D1 quota protection, CI race fix, link/copy fixes |

### Planning And Tracking Integration

- **GitHub Milestones** represent **target release versions** (for example, `v1.1.0`, `v0.2.0`).
- **Master Epics** organize phased roadmaps (`Phase 1..N`) and must declare:
  - Current Version and Target Release Version
  - Release Objectives, Phases, Dependencies, and Compatibility Requirements
  - Testing and Release Acceptance Criteria, Changelog Requirements, and Deployment Procedures
- **Labels** classify `priority:*`, `difficulty:*`, `type:*`, `area:*`, and `status:*`.
- **Release Gate**: Tagging and publishing (`vX.Y.Z`) occurs only after all milestone-required issues are closed, acceptance criteria are met, and CI passes. Urgent patches may release independently on `main` without blocking the next `MINOR` milestone.
