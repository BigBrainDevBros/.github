# Policy Compliance And Workspace Guidelines

This document serves as the mandatory pre-flight checklist and operational policy manual for all AI agents working across projects in this workspace (`/Users/even/Desktop/Projects`). Every agent must review and adhere to these guidelines before authoring code, modifying documentation, generating commits, or executing Git commands.

---

## Critical GitHub Suspension Warnings

GitHub monitors and suspends accounts for violations of their Acceptable Use Policies and Terms of Service. A past suspension occurred due to direct download links placed inside repository README files. To protect the user account (`AMFI-Disable`), the following rules are non-negotiable.

### 1. Direct Binary And Executable Links Prohibition

- **Never Add Binary Or Executable Links In READMEs Or Markdown**: Do not place direct download links to `.dmg`, `.pkg`, `.zip`, `.tar.gz`, `.app`, `.exe`, or any other compiled binary or installer file inside any README or Markdown file.
- **Use GitHub Releases Exclusively**: Binaries, precompiled assets, and distributable archives must only be attached to official GitHub Releases.
- **Permissible Links In Documentation**: Documentation may direct users to the repository's GitHub Releases page (e.g. `https://github.com/AMFI-Disable/<Repo>/releases`) or provide package manager instructions (e.g., `brew install ...`), but never raw binary file URLs.

### 2. Dual-Use Tools And Security Context

- Any utility involving system internals, permission overrides, or runtime patching (e.g., AMFI modifications) must explicitly state its legitimate administrative, debugging, or educational purpose.
- Never host or link to software designed to bypass software license keys, generate product keys, or facilitate unauthorized access.

### 3. macOS Gatekeeper And Unnotarized Open-Source Binaries

- **Permissible Gatekeeper Clearance Instructions**: Because open-source macOS software built without a paid Apple Developer ID certificate ($99/year) is quarantined by default, documentation and README files may provide Gatekeeper clearance commands (e.g. `xattr -cr /Applications/<App>.app` or `sudo xattr -r -c /Applications/<App>.app`).
- **Mandatory Security Context And Verification**: All Gatekeeper clearance instructions must:
  1. Clearly state that the security prompt occurs because the release is an unnotarized open-source build.
  2. Instruct the user to verify the cryptographic SHA-256 checksum against GitHub Releases first.
  3. Offer native macOS GUI alternatives (`System Settings > Privacy & Security > Open Anyway`, or `Control-click > Open`).
- **No Direct Binary Links**: Gatekeeper instructions must never be accompanied by raw binary/executable URLs; all downloads must route exclusively through GitHub Releases or package managers (`brew install`).

### 4. Anti-Spam And Automation Standards

- Do not automate inauthentic interactions, bulk activity, rank abuse (starring, following), or unsolicited promotional content across GitHub issues, PRs, or discussions.
- Do not utilize repository descriptions, README files, or Pages for commercial advertising or third-party marketing campaigns.

---

---

## Workspace Standards And Project Conventions

In addition to GitHub's platform policies, all agents working in this project environment must strictly adhere to the following workspace rules:

### 1. Git Identity And Remote URLs

- **Author Name**: Must always be set to `AMFI-Disable` (case-sensitive).
- **Author Email**: Must always be `evengao6688@gmail.com`.
- **Remote URLs**: Must strictly use `https://github.com/AMFI-Disable/<Repo>.git` (never lowercase `amfi-disable`).

### 2. Commit Message Structure

- All commit messages must follow the rigid structure: `xxx: xxx xxx xxx`
- **Format Breakdown**:
  1. A short type prefix (e.g. `feat:`, `fix:`, `ci:`, `docs:`, `chore:`, `refactor:`, `test:`).
  2. Exactly one space after the colon.
  3. **Exactly three lowercase words**.
- **Examples**:
  - `feat: add search filter`
  - `fix: resolve bundled script`
  - `ci: target modern matrix`
  - `docs: update setup guide`

### 3. File And Directory Naming

- All files and folders committed to Git repositories must use lowercase naming (e.g. `check.md`, `ci.yml`, `sources/models/clitoolmanager.swift`).

### 4. Document Header Title Formatting And No-Emoji Policy

- All Markdown and documentation headers (`#`, `##`, `###`) must use Title Case in natural human words (e.g., `# Project Setup Guidelines`).
- **No Emojis**: Do not use Unicode emojis or emoji shortcodes (`:white_check_mark:`, `:x:`, `:rocket:`, etc.) in any `readme.md`, `changelog.md`, `security.md`, release description, or `.github/` template. Use plain text (`Yes` / `No`, `Supported` / `Unsupported`).

### 5. Publishing And Release Gate

- **Do Not Publish Releases Unprompted**: Never automatically tag, release, or publish packages, artifacts, or GitHub Releases without explicit user consent.

### 6. Repository-Specific Exceptions

- **`Extensions/TornTools`**: Does **not** follow `check.md` or `template.md`. It strictly adheres to upstream creator conventions (`Mephiles/torntools_extension`):
  - **Framework & Language**: WXT with TypeScript.
  - **Formatting & Linting**: Oxfmt / Oxlint with 4-space tab indentation.
  - **Architecture**: Modular feature classes extending `Feature` under `src/common/features/`, settings registered in `default-database.ts`, and managed via `script-manager.ts`.
  - **File Naming & Commits**: Follows upstream conventions (uppercase filenames like `README.md`, `CONTRIBUTING.md`, atomic commits with PR template).

---

## Mandatory Pre-Flight Verification Checklist

Before saving, committing, or pushing changes, every agent must verify:

1. [ ] **No Direct Binary Links**: Are all README and Markdown files free of direct executable/binary links?
2. [ ] **Dual-Use Clarity**: Does security/system tooling have appropriate educational or administrative disclaimers?
3. [ ] **Git Author Identity**: Is `git config user.name` set to `AMFI-Disable` and email to `evengao6688@gmail.com`?
4. [ ] **Remote Repository Casing**: Does `git remote -v` point to `https://github.com/AMFI-Disable/...`?
5. [ ] **Strict Commit Message**: Does the commit message match `xxx: xxx xxx xxx` (prefix + exactly 3 lowercase words)?
6. [ ] **Lowercase File Paths**: Are all created or modified files and directories lowercase?
7. [ ] **Title Case Headers**: Are all headers formatted with Capitalized Words in human phrasing?
8. [ ] **No Emojis**: Are all documentation files, release notes, and `.github/` templates completely free of emojis?
9. [ ] **No Unapproved Releases**: Are all publishing/release actions held until specifically requested by the user?
10. [ ] **Version Parity**: On release commits, do manifest/in-app version constants match `changelog.md` and the target SemVer tag?
11. [ ] **Issue Standard Compliance**: Do new/open issues use a canonical `[PREFIX]` title, priority/difficulty/area labels, target milestone, assignee, and measurable acceptance criteria?

---

# GitHub Terms of Service

<!-- markdownlint-disable search-replace -->

Thank you for using GitHub! We're happy you're here. Please read this Terms of Service agreement carefully before accessing or using GitHub. Because it is such an important contract between us and our users, we have tried to make it as clear as possible. For your convenience, we have presented these terms in a short non-binding summary followed by the full legal terms.

## Summary

| Section | What can you find there? |
| --- | --- |
| [A. Definitions](#a-definitions) | Some basic terms, defined in a way that will help you understand this agreement. Refer back up to this section for clarification. |
| [B. Account Terms](#b-account-terms) | These are the basic requirements of having an Account on GitHub.  |
| [C. Acceptable Use](#c-acceptable-use)| These are the basic rules you must follow when using your GitHub Account. |
| [D. User-Generated Content](#d-user-generated-content) | You own the content you post on GitHub. However, you have some responsibilities regarding it, and we ask you to grant us some rights so we can provide services to you. |
| [E. Private Repositories](#e-private-repositories) | This section talks about how GitHub will treat content you post in private repositories. |
| [F. Copyright & DMCA Policy](#f-copyright-infringement-and-dmca-policy) | This section talks about how GitHub will respond if you believe someone is infringing your copyrights on GitHub. |
| [G. Intellectual Property Notice](#g-intellectual-property-notice) | This describes GitHub's rights in the website and service. |
| [H. API Terms](#h-api-terms) | These are the rules for using GitHub's APIs, whether you are using the API for development or data collection. |
| [I. Additional Product Terms](#i-github-additional-product-terms) | We have a few specific rules for GitHub's features and products. |
| [J. AI Features, Training, and Your Data](#j-ai-features-training-and-your-data) | These are the terms that apply to GitHub Copilot and other AI features, including how your data may be used for development and improvement of the artificial intelligence and machine learning models, and the controls available to you. |
| [K. Beta Previews](#k-beta-previews) | These are some of the additional terms that apply to GitHub's features that are still in development. |
| [L. Payment](#l-payment) | You are responsible for payment. We are responsible for billing you accurately. |
| [M. Cancellation and Termination](#m-cancellation-and-termination) | You may cancel this agreement and close your Account at any time. |
| [N. Communications with GitHub](#n-communications-with-github) | We only use email and other electronic means to stay in touch with our users. We do not provide phone support. |
| [O. Disclaimer of Warranties](#o-disclaimer-of-warranties) | We provide our service as is, and we make no promises or guarantees about this service. **Please read this section carefully; you should understand what to expect.** |
| [P. Limitation of Liability](#p-limitation-of-liability) | We will not be liable for damages or losses arising from your use or inability to use the service or otherwise arising under this agreement. **Please read this section carefully; it limits our obligations to you.** |
| [Q. Release and Indemnification](#q-release-and-indemnification) | You are fully responsible for your use of the service. |
| [R. Changes to these Terms of Service](#r-changes-to-these-terms) | We may modify this agreement, but we will give you 30 days' notice of material changes. |
| [S. Miscellaneous](#s-miscellaneous) | Please see this section for legal details including our choice of law. |

## The GitHub Terms of Service

Effective date: April 27, 2026

## A. Definitions

**Short version:** _We use these basic terms throughout the agreement, and they have specific meanings. You should know what we mean when we use each of the terms. There's not going to be a test on it, but it's still useful information._

1. An "Account" represents your legal relationship with GitHub. A “Personal Account” represents an individual User’s authorization to log in to and use the Service and serves as a User’s identity on GitHub. “Organizations” are shared workspaces that may be associated with a single entity or with one or more Users where multiple Users can collaborate across many projects at once. A Personal Account can be a member of any number of Organizations.
1. The “Agreement” refers, collectively, to all the terms, conditions, notices contained or referenced in this document (the “Terms of Service” or the "Terms") and all other operating rules, policies (including the GitHub Privacy Statement, available at [github.com/site/privacy](https://github.com/site/privacy)) and procedures that we may publish from time to time on the Website. Most of our site policies are available at [docs.github.com/categories/site-policy](/site-policy).
1. "AI Feature" means any feature of GitHub or our Affiliates that uses machine learning or artificial intelligence to generate Output, including GitHub Copilot, Copilot Autofix, and any other feature identified as using machine learning or artificial intelligence in our documentation.

1. “Affiliate” means any entity that directly or indirectly controls, is controlled by, or is under common control with a party, where "control" means having more than fifty percent (50%) ownership or the right to direct the management of the entity. For the avoidance of doubt, Microsoft is an Affiliate of GitHub.
1. "Beta Previews" mean software, services, or features identified as alpha, beta, preview, early access, or evaluation, or words or phrases with similar meanings.
1. "Content" means code, text, data, documentation, images, graphics, software, packages, and other materials made available through the Service.
1. “GitHub,” “We,” and “Us” refer to GitHub, Inc., as well as our directors, subsidiaries, contractors, licensors, officers, agents, and employees.
1. “Input” means any content or context provided to an AI Feature, including prompts, attachments, code in your workspace, and conversation history.
1. "Output" means responses and suggestions, including code or other material, generated by an AI Feature.
1. The “Service” refers to the applications, software, products, and services provided by GitHub, including through the Website and any Beta Previews.
1. “User,” “You,” and “Your” refer to the individual person, company, or organization that has visited or is using the Website or Service; that accesses or uses any part of the Account; or that directs the use of the Account in the performance of its functions. A User must be at least 13 years of age. Special terms may apply for business or government Accounts (See [Section B(5): Additional Terms](#5-additional-terms)).
1. "User-Generated Content" means Content that you or other users upload, submit, or create through the Service.
1. The “Website” refers to GitHub’s website located at [github.com](https://github.com/), and all content, services, and products provided by GitHub at or through the Website. It also refers to GitHub-owned subdomains of github.com, such as [education.github.com](https://education.github.com/) and [pages.github.com](https://pages.github.com/). These Terms also govern GitHub’s conference websites, such as [githubuniverse.com](https://githubuniverse.com/), and product websites, such as [electronjs.org](https://www.electronjs.org/). Occasionally, websites owned by GitHub may provide different or additional terms of service. If those additional terms conflict with this Agreement, the more specific terms apply to the relevant page or service.
1. "Your Content" means User-Generated Content that you upload, submit, or create, including your modifications to Content you have forked or cloned. It does not include the underlying Content created by others.

## B. Account Terms

**Short version:** _Personal Accounts and Organizations have different administrative controls; a human must create your Account; you must be 13 or over; you must provide a valid email address; and you may not have more than one free Account. You alone are responsible for your Account and anything that happens while you are signed in to or using your Account. You are responsible for keeping your Account secure._

### 1. Account Controls

* Users. Subject to these Terms, you retain ultimate administrative control over your Personal Account and the Content within it.

* Organizations. The "owner" of an Organization that was created under these Terms has ultimate administrative control over that Organization and the Content within it. Within the Service, an owner can manage User access to the Organization’s data and projects. An Organization may have multiple owners, but there must be at least one Personal Account designated as an owner of an Organization. If you are the owner of an Organization under these Terms, we consider you responsible for the actions that are performed on or through that Organization.

### 2. Required Information

You must provide a valid email address in order to complete the signup process. Any other information requested, such as your real name, is optional, unless you are accepting these terms on behalf of a legal entity (in which case we need more information about the legal entity) or if you opt for a [paid Account](#l-payment), in which case additional information will be necessary for billing purposes.

### 3. Account Requirements

We have a few simple rules for Accounts on GitHub's Service.
* You must be a human to create an Account. Accounts registered by "bots" or other automated methods are not permitted. We do permit machine accounts:
* A machine account is an Account set up by an individual human who accepts the Terms on behalf of the Account, provides a valid email address, and is responsible for its actions. A machine account is used exclusively for performing automated tasks. Multiple users may direct the actions of a machine account, but the owner of the Account is ultimately responsible for the machine's actions. You may maintain no more than one free machine account in addition to your free Personal Account.
* One person or legal entity may maintain no more than one free Account (if you choose to control a machine account as well, that's fine, but it can only be used for running a machine).
* You must be age 13 or older. While we are thrilled to see brilliant young coders get excited by learning to program, we must comply with United States law. GitHub does not target our Service to children under 13, and we do not permit any Users under 13 on our Service. If we learn of any User under the age of 13, we will [terminate that User’s Account immediately](#m-cancellation-and-termination). If you are a resident of a country outside the United States, your country’s minimum age may be older; in such a case, you are responsible for complying with your country’s laws.
* Your login may only be used by one person — i.e., a single login may not be shared by multiple people. A paid Organization may only provide access to as many Personal Accounts as your subscription allows.
* You may not use GitHub in violation of export control or sanctions laws of the United States or any other applicable jurisdiction. You may not use GitHub if you are or are working on behalf of a [Specially Designated National (SDN)](https://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/default.aspx) or a person subject to similar blocking or denied party prohibitions administered by a U.S. government agency. GitHub may allow persons in certain sanctioned countries or territories to access certain GitHub services pursuant to U.S. government authorizations. For more information, please see our [Export Controls policy](/site-policy/other-site-policies/github-and-trade-controls).

### 4. Account Security

You are responsible for keeping your Account secure while you use our Service. We offer tools such as two-factor authentication to help you maintain your Account's security, but the content of your Account and its security are up to you.
* You are responsible for all content posted and activity that occurs under your Account (even when content is posted by others who have Accounts under your Account).
* You are responsible for maintaining the security of your Account and password. GitHub cannot and will not be liable for any loss or damage from your failure to comply with this security obligation.
* You will promptly notify GitHub by contacting us through the [GitHub Support portal](https://support.github.com/) if you become aware of any unauthorized use of, or access to, our Service through your Account, including any unauthorized use of your password or Account.

### 5. Additional Terms

In some situations, third parties' terms may apply to your use of GitHub. For example, you may be a member of an organization on GitHub with its own terms or license agreements; you may download an application that integrates with GitHub; or you may use GitHub to authenticate to another service. Please be aware that while these Terms are our full agreement with you, other parties' terms govern their relationships with you.

If you are a government User or otherwise accessing or using any GitHub Service in a government capacity, this [Government Amendment to GitHub Terms of Service](/site-policy/site-policy-deprecated/amendment-to-github-terms-of-service-applicable-to-us-federal-government-users) applies to you, and you agree to its provisions.

If you have signed up for GitHub Enterprise Cloud, the [Enterprise Cloud Addendum](/site-policy/site-policy-deprecated/github-enterprise-service-level-agreement) applies to you, and you agree to its provisions.

## C. Acceptable Use

**Short version:** _GitHub hosts a wide variety of collaborative projects from all over the world, and that collaboration only works when our users are able to work together in good faith. While using the service, you must follow the terms of this section, which include some restrictions on content you can post, conduct on the service, and other limitations. In short, be excellent to each other._

Your use of the Website and Service must not violate any applicable laws, including copyright or trademark laws, export control or sanctions laws, or other laws in your jurisdiction. You are responsible for making sure that your use of the Service is in compliance with laws and any applicable regulations.

You agree that you will not under any circumstances violate our [Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies) or [Community Guidelines](/site-policy/github-terms/github-community-guidelines).


## D. User-Generated Content

**Short version:** _You own content you create, but you allow us certain rights to it, so that we can display and share the content you post. You still have control over your content, and responsibility for it, and the rights you grant us are limited to those we need to provide the service. We have the right to remove content or close Accounts if we need to._

### 1. Responsibility for User-Generated Content

You are responsible for Your Content and any harm resulting from it. This includes Content you post, upload, or make available through the Service. We are not responsible for any public display or misuse of Your Content.

### 2. GitHub May Remove Content

We may refuse or remove User-Generated Content that violates applicable law or our terms and policies. We access private repositories only as described in Section E. Content displayed on GitHub Mobile may be subject to app store terms.

### 3. Ownership and License Grants

You own Your Content. If you post Content you did not create, you are responsible for ensuring you have the right to post it and for complying with any applicable licenses.

You grant us and other Users the licenses in Sections D.4–D.8. These licenses apply to Your Content. If Your Content already includes a license granting us the permissions we need, no additional license is required. You will not receive payment for these rights. These licenses end when you remove Your Content, unless other Users have forked it.

### 4. License Grant to Us

You grant GitHub and our Affiliates the right to store, host, archive, parse, display, and make copies of Your Content as necessary to provide, develop, and improve the Service, including by training AI Features, and for the purpose of training, developing, and improving artificial intelligence and machine learning models and technologies of our Affiliates. This license includes the right to do things like copy it to our database and make backups; show it to you and other Users; parse it into a search index or otherwise analyze it on our servers; share it with other Users; and perform it, in case Your Content is something like music or video. For the avoidance of doubt, use of Your Content to develop, train, and improve artificial intelligence and machine learning models and technologies of GitHub and our Affiliates is within the scope of this license and does not constitute a sale or other restricted transfer of Your Content.

### 5. License Grant to Other Users

Your Content that you post publicly, including issues, comments, and contributions to other Users' repositories, may be viewed by others. By setting your repositories to be viewed publicly, you agree to allow others to view and "fork" your repositories (this means that others may make their own copies within the Service in repositories they control).

By making a repository public, you grant other Users a nonexclusive, worldwide license to use, display, perform and reproduce (by forking) Your Content through the Service as permitted by GitHub's functionality. You may grant additional rights by [adopting a license](/communities/setting-up-your-project-for-healthy-contributions/adding-a-license-to-a-repository#including-an-open-source-license-in-your-repository). If you post Content you did not create or own, you are responsible for ensuring it is licensed under terms that permit these uses.

### 6. Contributions Under Repository License

Whenever you add Content to a repository containing notice of a license, you license that Content under the same terms, and you agree that you have the right to license that Content under those terms. If you have a separate agreement to license that Content under different terms, such as a contributor license agreement, that agreement will supersede.

Isn't this just how it works already? Yep. This is widely accepted as the norm in the open-source community; it's commonly referred to by the shorthand "inbound=outbound". We're just making it explicit.

### 7. Moral Rights

You retain all moral rights to Your Content that you upload, publish, or submit to any part of the Service, including the rights of integrity and attribution. However, you waive these rights and agree not to assert them against us or our Affiliates, to enable GitHub and our Affiliates to reasonably exercise the rights granted in Section D.4, but not otherwise.

To the extent this agreement is not enforceable by applicable law, you grant GitHub the rights we need to use Your Content without attribution and to make reasonable adaptations of Your Content as necessary to render the Website and provide the Service.

### 8. Public Repositories and Lawful Access

By choosing to contribute Content to a public repository, you are choosing to and directing us to make such Content accessible to everyone on the internet. Unless specifically set forth herein, these Terms do not restrict lawful access to or use of the contents of public repositories by third parties, or by GitHub or its Affiliates.

### 9. Access Reciprocity

By using automated means to access, collect, or otherwise use (“Access”) any publicly accessible Content from the Service for the purpose of developing or training any commercially available artificial intelligence model, machine learning system, or similar technology (a "Commercial AI System"), you hereby waive any and all policies, terms, conditions, or contractual provisions governing products, services, websites or datasets you own or operate that would otherwise prohibit, restrict, or place conditions upon GitHub's Access to any publicly accessible data, information or content associated with your products or services, including for the purpose of developing or training any Commercial AI System. You further agree not to impose technical or other targeted measures to restrict or retaliate against such Access.

This Section D.9 does not apply to Access solely for the purpose of academic research or if, on the date you Access the Content, the number of monthly active users of the products or services made available by you is less than 700 million in the preceding calendar month. For the purposes of this Section, "you" shall refer to you and any entity that directly or indirectly controls, is controlled by, or is under common control with you (affiliates).

## E. Private Repositories

**Short version:** _We treat the content of private repositories as confidential, and we only access it as described in Section E.3 below—for security purposes, to assist the repository owner with a support matter, to maintain the integrity of the Service, to comply with our legal obligations, if we have reason to believe the contents are in violation of the law, or with your consent._

### 1. Control of Private Repositories

Some Accounts may have private repositories, which allow the User to control access to Content.

### 2. Confidentiality of Private Repositories

GitHub considers the contents of private repositories to be confidential to you. GitHub will protect the contents of private repositories from unauthorized use, access, or disclosure in the same manner that we would use to protect our own confidential information of a similar nature and in no event with less than a reasonable degree of care.

### 3. Access

You control access to the content of your private repositories. GitHub considers the contents of private repositories to be confidential to you, as set forth in Section E.2, and GitHub personnel will not access private repository content without your consent except in the following circumstances:

* for security purposes;
* for automated scanning or manual review for known vulnerabilities, active malware, or other content known to violate our Terms of Service;
* to assist the repository owner with a support matter;
* to maintain the integrity of the Service; or
* to comply with our legal obligations if we have reason to believe the contents are in violation of the law.

You may choose to enable additional access to your private repositories. For example:
* You may enable various GitHub services or features that require additional rights to Your Content in private repositories. These rights may vary depending on the service or feature, but GitHub will continue to treat your private repository Content as confidential. If those services or features require rights in addition to those we need to provide the GitHub Service, we will provide an explanation of those rights.
* If you provide your private repository content as Input to AI Features, we may use that Input to provide, develop, train, and improve the Service, including AI Features. Your ability to opt out under [Section J.3](#3-development-and-improvement-using-your-input-and-output) applies to this use of private repository content. We will not otherwise use your private repository contents to develop or improve the Service.

Additionally, we may be [compelled by law](/site-policy/privacy-policies/github-general-privacy-statement#for-legal-disclosure) to disclose the contents of your private repositories.

GitHub will provide notice regarding our access to private repository content, unless [for legal disclosure](/site-policy/privacy-policies/github-general-privacy-statement#for-legal-disclosure), to comply with our legal obligations, or where otherwise bound by requirements under law, for automated scanning, or if in response to a security threat or other risk to security.

## F. Copyright Infringement and DMCA Policy

If you believe that content on our website violates your copyright, please contact us in accordance with our [Digital Millennium Copyright Act Policy](/site-policy/content-removal-policies/dmca-takedown-policy). If you are a copyright owner and you believe that content on GitHub violates your rights, please contact us via [our convenient DMCA form](https://github.com/contact/dmca) or by emailing [copyright@github.com](mailto:copyright@github.com). There may be legal consequences for sending a false or frivolous takedown notice. Before sending a takedown request, you must consider legal uses such as fair use and licensed uses.

We will terminate the Accounts of [repeat infringers](/site-policy/content-removal-policies/dmca-takedown-policy#f-repeated-infringement) of this policy.

## G. Intellectual Property Notice

**Short version:** _We own the service and all of our content. In order for you to use our content, we give you certain rights to it, but you may only use our content in the way we have allowed._

### 1. GitHub's Rights to Content

GitHub and our licensors, vendors, agents, and/or our content providers retain ownership of all intellectual property rights of any kind related to the Website and Service. We reserve all rights that are not expressly granted to you under this Agreement or by law. The look and feel of the Website and Service is copyright © GitHub, Inc. All rights reserved. You may not duplicate, copy, or reuse any portion of the HTML/CSS, JavaScript, or visual design elements or concepts without express written permission from GitHub.

### 2. GitHub Trademarks and Logos

If you’d like to use GitHub’s trademarks, you must follow all of our trademark guidelines, including those on our logos page: https://github.com/logos.

### 3. License to GitHub Policies

This Agreement is licensed under this [Creative Commons Zero license](https://creativecommons.org/publicdomain/zero/1.0/). For details, see our [site-policy repository](https://github.com/github/site-policy#license).

## H. API Terms

**Short version:** _You agree to these Terms of Service, plus this Section H, when using any of GitHub's APIs (Application Programming Interface), including use of the API through a third party product that accesses GitHub._

Abuse or excessively frequent requests to GitHub via the API may result in the temporary or permanent suspension of your Account's access to the API. GitHub, in our sole discretion, will determine abuse or excessive usage of the API. We will make a reasonable attempt to warn you via email prior to suspension.

You may not share API tokens to exceed GitHub's rate limitations.

You may not use the API to download data or Content from GitHub for spamming purposes, including for the purposes of selling GitHub users' personal information, such as to recruiters, headhunters, and job boards.

All use of the GitHub API is subject to these Terms of Service and the [GitHub Privacy Statement](https://github.com/site/privacy).

GitHub may offer subscription-based access to our API for those Users who require high-throughput access or access that would result in resale of GitHub's Service.

## I. GitHub Additional Product Terms

**Short version:** _You need to follow certain specific terms and conditions for GitHub's various features and products, and you agree to the Supplemental Terms and Conditions when you agree to this Agreement._

Some Service features may be subject to additional terms specific to that feature or product as set forth in the GitHub Additional Product Terms. By accessing or using the Services, you also agree to the [GitHub Additional Product Terms](/site-policy/github-terms/github-terms-for-additional-products-and-features).

## J. AI Features, Training, and Your Data

### 1. Applicability

This section applies to all AI Features unless a specific feature has additional terms that expressly modify them. The training and data-use provisions in Section J.3 apply only to individual licenses. If your use of the Service is governed by a GitHub Customer Agreement or volume licensing agreement, those agreements govern the use of your data in connection with AI Features and Section J.3 does not apply to you.


### 2. Ownership

GitHub does not claim ownership of your Input or Output.

Output may contain material that resembles code or content in the model's training data or that is subject to third-party copyrights or open source license terms. You are responsible for determining whether your use of Output requires a third-party license and for complying with any such license.

### 3. Development and Improvement Using Your Input and Output

We use your Inputs to generate Outputs and provide the AI Features. You also grant GitHub and its Affiliates a license to collect and use your Inputs and Outputs to develop, train and improve artificial intelligence and machine learning models and technologies including those that power AI Features, unless (a) you opt out through your account settings, or (b) your use of the Service is governed by a GitHub Customer Agreement or volume licensing agreement. If you opt out, GitHub will not collect or use your Inputs and Outputs for the purposes described in this paragraph from the effective date of your opt-out going forward.

Unless you opt out, GitHub's Affiliates may use your Inputs and Outputs under this license in accordance with their applicable privacy and contractual obligations. This license does not, however, permit GitHub or its Affiliates to share your Inputs or Outputs with third-party AI model providers for their own independent model training purposes.

The license in this Section J.3 is in addition to, and does not limit, the rights granted to GitHub and its Affiliates under Sections D.4 and D.8. This license does not extend to Your Content stored in repositories that are not provided as Input to an AI Feature.

The opt-out right described in this section applies solely to the use of your Inputs and Outputs as described in this section, and does not apply to the license granted in Sections D.4-D.8 or to any Content that does not constitute Input or Output (including Content stored in public repositories).

### 4. Disclaimers

Output is provided "as-is" and subject to the disclaimers in Section O. Without limiting Section O: Output may be inaccurate, incomplete, or non-functional. Output may resemble third-party code, including code under open source licenses. We do not guarantee that Output is free of errors, vulnerabilities, or intellectual property claims.

You are responsible for reviewing, testing, and validating any Output before use.

### 5. Your Responsibility and Indemnity

You are responsible for your use of Output, including ensuring it complies with applicable law and does not infringe third-party rights.

Your indemnity obligations in Section Q apply to your use of AI Features and Output, including claims arising from Output you incorporate into your products or services.

## K. Beta Previews

**Short version:** _Beta Previews may not be supported or may change at any time. You may receive confidential information through those programs that must remain confidential while the program is private. We'd love your feedback to make our Beta Previews better._

### 1. Subject to Change

Beta Previews may not be supported and may be changed at any time without notice. In addition, Beta Previews are not subject to the same security measures and auditing to which the Service has been and is subject. **By using a Beta Preview, you use it at your own risk.**

### 2. Confidentiality

As a user of Beta Previews, you may get access to special information that isn’t available to the rest of the world. Due to the sensitive nature of this information, it’s important for us to make sure that you keep that information secret.

**Confidentiality Obligations.** You agree that any non-public Beta Preview information we give you, such as information about a private Beta Preview, will be considered GitHub’s confidential information (collectively, “Confidential Information”), regardless of whether it is marked or identified as such. You agree to only use such Confidential Information for the express purpose of testing and evaluating the Beta Preview (the “Purpose”), and not for any other purpose. You should use the same degree of care as you would with your own confidential information, but no less than reasonable precautions to prevent any unauthorized use, disclosure, publication, or dissemination of our Confidential Information. You promise not to disclose, publish, or disseminate any Confidential Information to any third party, unless we don’t otherwise prohibit or restrict such disclosure (for example, you might be part of a GitHub-organized group discussion about a private Beta Preview feature).

**Exceptions.** Confidential Information will not include information that is: (a) or becomes publicly available without breach of this Agreement through no act or inaction on your part (such as when a private Beta Preview becomes a public Beta Preview); (b) known to you before we disclose it to you; (c) independently developed by you without breach of any confidentiality obligation to us or any third party; or (d) disclosed with permission from GitHub. You will not violate the terms of this Agreement if you are required to disclose Confidential Information pursuant to operation of law, provided GitHub has been given reasonable advance written notice to object, unless prohibited by law.

### 3. Feedback

We’re always trying to improve our products and services, and your feedback as a Beta Preview user will help us do that. If you choose to give us any ideas, know-how, algorithms, code contributions, suggestions, enhancement requests, recommendations or any other feedback for our products or services (collectively, “Feedback”), you acknowledge and agree that GitHub will have a royalty-free, fully paid-up, worldwide, transferable, sub-licensable, irrevocable and perpetual license to implement, use, modify, commercially exploit and/or incorporate the Feedback into our products, services, and documentation.

## L. Payment

**Short version:** _You are responsible for any fees associated with your use of GitHub. We are responsible for communicating those fees to you clearly and accurately, and letting you know well in advance if those prices change._

### 1. Pricing

Our pricing and payment terms are available at [github.com/pricing](https://github.com/pricing). If you agree to a subscription price, that will remain your price for the duration of the payment term; however, prices are subject to change at the end of a payment term.

### 2. Upgrades, Downgrades, and Changes

* We will immediately bill you when you upgrade from the free plan to any paying plan.
* If you change from a monthly billing plan to a yearly billing plan, GitHub will bill you for a full year at the next monthly billing date.
* If you upgrade to a higher level of service, we will bill you for the upgraded plan immediately.
* You may change your level of service at any time by [choosing a plan option](https://github.com/pricing) or going into your [Billing settings](https://github.com/settings/billing). If you choose to downgrade your Account, you may lose access to Content, features, or capacity of your Account. Please see our section on [Cancellation](#m-cancellation-and-termination) for information on getting a copy of that Content.

### 3. Billing Schedule; No Refunds

**Payment Based on Plan** For monthly or yearly payment plans, the Service is billed in advance on a monthly or yearly basis respectively and is non-refundable. There will be no refunds or credits for partial months of service, downgrade refunds, or refunds for months unused with an open Account; however, the service will remain active for the length of the paid billing period. In order to treat everyone equally, no exceptions will be made.

**Payment Based on Usage** Some Service features are billed based on your usage. A limited quantity of these Service features may be included in your plan for a limited term without additional charge. If you choose to use paid Service features beyond the quantity included in your plan, you pay for those Service features based on your actual usage in the preceding month. Monthly payment for these purchases will be charged on a periodic basis in arrears. See [GitHub Additional Product Terms for Details](/site-policy/github-terms/github-terms-for-additional-products-and-features).

**Invoicing** For invoiced Users, User agrees to pay the fees in full, up front without deduction or setoff of any kind, in U.S. Dollars. User must pay the fees within thirty (30) days of the GitHub invoice date. Amounts payable under this Agreement are non-refundable, except as otherwise provided in this Agreement. If User fails to pay any fees on time, GitHub reserves the right, in addition to taking any other action at law or equity, to (i) charge interest on past due amounts at 1.0% per month or the highest interest rate allowed by law, whichever is less, and to charge all expenses of recovery, and (ii) terminate the applicable order form. User is solely responsible for all taxes, fees, duties and governmental assessments (except for taxes based on GitHub's net income) that are imposed or become due in connection with this Agreement.

### 4. Authorization

By agreeing to these Terms, you are giving us permission to charge your on-file credit card, PayPal account, or other approved methods of payment for fees that you authorize for GitHub.

### 5. Responsibility for Payment

You are responsible for all fees, including taxes, associated with your use of the Service. By using the Service, you agree to pay GitHub any charge incurred in connection with your use of the Service. If you dispute the matter, contact us through the [GitHub Support portal](https://support.github.com/). You are responsible for providing us with a valid means of payment for paid Accounts. Free Accounts are not required to provide payment information.

## M. Cancellation and Termination

**Short version:** _You may close your Account at any time. If you do, we'll treat your information responsibly._

### 1. Account Cancellation

It is your responsibility to properly cancel your Account with GitHub. You can [cancel your Account at any time](/billing/managing-the-plan-for-your-github-account/downgrading-your-accounts-plan) by going into your Settings in the global navigation bar at the top of the screen. The Account screen provides a simple, no questions asked cancellation link. We are not able to cancel Accounts in response to an email or phone request.

### 2. Upon Cancellation

We will retain and use your information as necessary to comply with our legal obligations, resolve disputes, and enforce our agreements, but barring legal requirements, we will delete your full profile and the Content of your repositories within 90 days of cancellation or termination (though some information may remain in encrypted backups). This information cannot be recovered once your Account is canceled.

We will not delete Content that you have contributed to other Users' repositories or that other Users have forked.

Upon request, we will make a reasonable effort to provide an Account owner with a copy of your lawful, non-infringing Account contents after Account cancellation, termination, or downgrade. You must make this request within 90 days of cancellation, termination, or downgrade.

### 3. GitHub May Terminate

GitHub has the right to suspend or terminate your access to all or any part of the Website at any time, with or without cause, with or without notice, effective immediately. GitHub reserves the right to refuse service to anyone for any reason at any time.

### 4. Survival

All provisions of this Agreement which, by their nature, should survive termination _will_ survive termination — including, without limitation: ownership provisions, warranty disclaimers, indemnity, and limitations of liability.

## N. Communications with GitHub

**Short version:** _We use email and other electronic means to stay in touch with our users._

### 1. Electronic Communication Required

For contractual purposes, you (1) consent to receive communications from us in an electronic form via the email address you have submitted or via the Service; and (2) agree that all Terms of Service, agreements, notices, disclosures, and other communications that we provide to you electronically satisfy any legal requirement that those communications would satisfy if they were on paper. This section does not affect your non-waivable rights.

### 2. Legal Notice to GitHub Must Be in Writing

Communications made through email or GitHub Support's messaging system will not constitute legal notice to GitHub or any of its officers, employees, agents or representatives in any situation where notice to GitHub is required by contract or any law or regulation. Legal notice to GitHub must be in writing and [served on GitHub's legal agent](/site-policy/other-site-policies/guidelines-for-legal-requests-of-user-data#submitting-requests).

### 3. No Phone Support

GitHub only offers support via email, in-Service communications, and electronic messages. We do not offer telephone support.

## O. Disclaimer of Warranties

**Short version:** _We provide our service as is, and we make no promises or guarantees about this service. Please read this section carefully; you should understand what to expect._

GitHub provides the Website and the Service “as is” and “as available,” without warranty of any kind. Without limiting this, we expressly disclaim all warranties, whether express, implied or statutory, regarding the Website and the Service including without limitation any warranty of merchantability, fitness for a particular purpose, title, security, accuracy and non-infringement.

GitHub does not warrant that the Service will meet your requirements; that the Service will be uninterrupted, timely, secure, or error-free; that the information provided through the Service is accurate, reliable or correct; that any defects or errors will be corrected; that the Service will be available at any particular time or location; or that the Service is free of viruses or other harmful components. You assume full responsibility and risk of loss resulting from your downloading and/or use of files, information, content or other material obtained from the Service.

## P. Limitation of Liability

**Short version:** _We will not be liable for damages or losses arising from your use or inability to use the service or otherwise arising under this agreement. Please read this section carefully; it limits our obligations to you._

You understand and agree that we will not be liable to you or any third party for any loss of profits, use, goodwill, or data, or for any incidental, indirect, special, consequential or exemplary damages, however arising, that result from

<!-- markdownlint-disable GHD034 -->

* the use, disclosure, or display of your User-Generated Content;
* your use or inability to use the Service;
* any modification, price change, suspension or discontinuance of the Service;
* the Service generally or the software or systems that make the Service available;
* unauthorized access to or alterations of your transmissions or data;
* statements or conduct of any third party on the Service;
* any other user interactions that you input or receive through your use of the Service; or
* any other matter relating to the Service.

<!-- markdownlint-enable GHD034 -->

Our liability is limited whether or not we have been informed of the possibility of such damages, and even if a remedy set forth in this Agreement is found to have failed of its essential purpose. We will have no liability for any failure or delay due to matters beyond our reasonable control.

## Q. Release and Indemnification

**Short version:** _You are responsible for your use of the service. If you harm someone else or get into a dispute with someone else, we will not be involved._

If you have a dispute with one or more Users, you agree to release GitHub from any and all claims, demands and damages (actual and consequential) of every kind and nature, known and unknown, arising out of or in any way connected with such disputes.

You agree to indemnify us, defend us, and hold us harmless from and against any and all claims, liabilities, and expenses, including attorneys’ fees, arising out of your use of the Website and the Service, including but not limited to your violation of this Agreement, provided that GitHub (1) promptly gives you written notice of the claim, demand, suit or proceeding; (2) gives you sole control of the defense and settlement of the claim, demand, suit or proceeding (provided that you may not settle any claim, demand, suit or proceeding unless the settlement unconditionally releases GitHub of all liability); and (3) provides to you all reasonable assistance, at your expense.

## R. Changes to These Terms

**Short version:** _We want our users to be informed of important changes to our terms, but some changes aren't that important — we don't want to bother you every time we fix a typo. So while we may modify this agreement at any time, we will notify users of any material changes and give you time to adjust to them._

We reserve the right, at our sole discretion, to amend these Terms of Service at any time and will update these Terms of Service in the event of any such amendments. We will notify our Users of material changes to this Agreement, such as price increases, at least 30 days prior to the change taking effect by posting a notice on our Website or sending email to the primary email address specified in your GitHub account. Customer's continued use of the Service after those 30 days constitutes agreement to those revisions of this Agreement. For any other modifications, your continued use of the Website constitutes agreement to our revisions of these Terms of Service. You can view all changes to these Terms in our [Site Policy](https://github.com/github/site-policy) repository.

We reserve the right at any time and from time to time to modify or discontinue, temporarily or permanently, the Website (or any part of it) with or without notice.

## S. Miscellaneous

### 1. Governing Law

Except to the extent applicable law provides otherwise, this Agreement between you and GitHub and any access to or use of the Website or the Service are governed by the federal laws of the United States of America and the laws of the State of California, without regard to conflict of law provisions. You and GitHub agree to submit to the exclusive jurisdiction and venue of the courts located in the City and County of San Francisco, California. However, any claim for injunctive relief with respect to a violation of section D.9 may be brought in any jurisdiction.

### 2. Non-Assignability

GitHub may assign or delegate these Terms of Service and/or the [GitHub Privacy Statement](https://github.com/site/privacy), in whole or in part, to any person or entity at any time with or without your consent, including the license grant in Section D.4. You may not assign or delegate any rights or obligations under the Terms of Service or Privacy Statement without our prior written consent, and any unauthorized assignment and delegation by you is void.

### 3. Section Headings and Summaries

Throughout this Agreement, each section includes titles and brief summaries of the following terms and conditions. These section titles and brief summaries are not legally binding.

### 4. Severability, No Waiver, and Survival

If any part of this Agreement is held invalid or unenforceable, that portion of the Agreement will be construed to reflect the parties’ original intent. The remaining portions will remain in full force and effect. Any failure on the part of GitHub to enforce any provision of this Agreement will not be considered a waiver of our right to enforce such provision. Our rights under this Agreement will survive any termination of this Agreement.

### 5. Amendments; Complete Agreement

This Agreement may only be modified by a written amendment signed by an authorized representative of GitHub, or by the posting by GitHub of a revised version in accordance with [Section R. Changes to These Terms](#r-changes-to-these-terms). These Terms of Service, together with the GitHub Privacy Statement, represent the complete and exclusive statement of the agreement between you and us. This Agreement supersedes any proposal or prior agreement oral or written, and any other communications between you and GitHub relating to the subject matter of these terms including any confidentiality or nondisclosure agreements.

### 6. Questions

Questions about the Terms of Service? Contact us through the [GitHub Support portal](https://support.github.com/).

---

# GitHub Acceptable Use Policies

**Short version:** _We host a wide variety of collaborative projects from all over the world, and that collaboration only works when our users are able to work together in good faith. While using the Service, you must comply with our Acceptable Use Policies, which include some restrictions on content and conduct on GitHub related to user safety, intellectual property, privacy, authenticity, and other limitations. In short, be excellent to each other._

Capitalized terms used but not defined in these Acceptable Use Policies have the meanings assigned to them in your main agreement with us — the [GitHub Terms of Service](/site-policy/github-terms/github-terms-of-service) or GitHub Customer Agreement, or the [GitHub Corporate Terms of Service](/site-policy/github-terms/github-corporate-terms-of-service) or other legacy GitHub contract, or a Microsoft volume licensing agreement. For customers subject to the legacy Corporate Terms of Service, "you" and "your" refer to "Customer" or "Users". "We", "us", and "our" refer to "GitHub".

## 1. Compliance with Laws and Regulations

You are responsible for using the Service in compliance with all applicable laws, regulations, and all of our Acceptable Use Policies. These policies may be updated from time to time and are provided below.

## 2. User Safety

We do not allow content or activity on GitHub that:

<!-- markdownlint-disable GHD034 -->

* is unlawful or promotes unlawful activities;

* is [sexually obscene](/site-policy/acceptable-use-policies/github-sexually-obscene-content) or relates to sexual exploitation or abuse, including of minors;

* is libelous, defamatory, or fraudulent;

* is [discriminatory or abusive](/site-policy/acceptable-use-policies/github-hate-speech-and-discrimination) toward any individual or group;

* is [false, inaccurate, or intentionally deceptive information](/site-policy/acceptable-use-policies/github-misinformation-and-disinformation) and likely to adversely affect the public interest (including health, safety, election integrity, and civic participation);

* [harasses or abuses](/site-policy/acceptable-use-policies/github-bullying-and-harassment) another individual or group, including our employees, officers, and agents, or other users;

* [threatens or incites violence](/site-policy/acceptable-use-policies/github-threats-of-violence-and-gratuitously-violent-content) toward any individual or group, especially on the basis of who they are;

* [gratuitously depicts or glorifies violence](/site-policy/acceptable-use-policies/github-threats-of-violence-and-gratuitously-violent-content), including violent images; or

* is off-topic, or interacts with platform features in a way that significantly or repeatedly [disrupts the experience of other users](/site-policy/acceptable-use-policies/github-disrupting-the-experience-of-other-users).

## 3. Intellectual Property, Authenticity, and Private Information

We do not allow content or activity on GitHub that:

* infringes any proprietary right of any party, including patent, trademark, trade secret, copyright, right of publicity, or other right;

* unlawfully shares unauthorized product licensing keys, software for generating unauthorized product licensing keys, or software for bypassing checks for product licensing keys, including extension of a free license beyond its trial period;

* [impersonates any person or entity](/site-policy/acceptable-use-policies/github-impersonation), including any of our employees or representatives, including through false association with GitHub, or by fraudulently misrepresenting your identity or site's purpose; or

* [violates the privacy of any third party](/site-policy/acceptable-use-policies/github-doxxing-and-invasion-of-privacy), such as by posting another person's personal information without consent.

## 4. Spam and Inauthentic Activity on GitHub

We do not allow content or activity on GitHub that is:
* automated excessive bulk activity and coordinated inauthentic activity, such as
   * spamming
   * cryptocurrency mining;
* bulk distribution of promotions and advertising prohibited by GitHub terms and policies;
* inauthentic interactions, such as fake accounts and automated inauthentic activity;
* rank abuse, such as automated starring or following;
* creation of or participation in secondary markets for the purpose of the proliferation of inauthentic activity;
* using GitHub as a platform for propagating abuse on other platforms;
* phishing or attempted phishing; or
* using our servers for any form of excessive automated bulk activity, to place undue burden on our servers through automated means, or to relay any form of unsolicited advertising or solicitation through our servers, such as get-rich-quick schemes;
* incentivized by (or incentivizes inauthentic engagement with) rewards such as cryptocurrency airdrops, tokens, credits, gifts or other give-aways.

## 5. Site Access and Safety

We do not allow content or activity on GitHub that:

* directly supports [unlawful active attack or malware campaigns](/site-policy/acceptable-use-policies/github-active-malware-or-exploits) that are causing technical harms — such as using our platform to deliver malicious executables or as attack infrastructure, for example by organizing denial of service attacks or managing command and control servers — with no implicit or explicit dual-use purpose prior to the abuse occurring; or
* uses our servers to disrupt or to attempt to disrupt, or to gain or to attempt to gain unauthorized access to, any service, device, data, account or network. Please note, activities permitted under bug bounty programs, such as the [GitHub Bug Bounty program](https://bounty.github.com), are not considered “unauthorized,” but must only affect the organization whose bug bounty program authorized the activity.

<!-- markdownlint-enable GHD034 -->

## 6. Services Usage Limits

You will not reproduce, duplicate, copy, sell, resell or exploit any portion of the Service, use of the Service, or access to the Service without our express written permission.

## 7. Information Usage Restrictions

You may use information from our Service for the following reasons, regardless of whether the information was scraped, collected through our API, or obtained otherwise:

* Researchers may use public, non-personal information from the Service for research purposes, only if any publications resulting from that research are [open access](https://en.wikipedia.org/wiki/Open_access).
* Archivists may use public information from the Service for archival purposes.

Scraping refers to extracting information from our Service via an automated process, such as a bot or webcrawler. Scraping does not refer to the collection of information through our API. Please see Section H of our [Terms of Service](/site-policy/github-terms/github-terms-of-service#h-api-terms) for our API Terms.

You may not use information from the Service (whether scraped, collected through our API, or obtained otherwise) for spamming purposes, including for the purposes of sending unsolicited emails to users or selling personal information, such as to recruiters, headhunters, and job boards.

Your use of information from the Service must comply with the [GitHub Privacy Statement](/site-policy/privacy-policies/github-privacy-statement).

## 8. Privacy

Misuse of personal information is prohibited.

Any person, entity, or service collecting data from the Service must comply with the [GitHub Privacy Statement](/site-policy/privacy-policies/github-privacy-statement), particularly in regards to the collection of personal information. If you collect any personal information from the Service, you agree that you will only use that personal information for the purpose for which that User has authorized it. You agree that you will reasonably secure any personal information you have gathered from the Service, and you will respond promptly to complaints, removal requests, and "do not contact" requests from us or other users.

## 9. Excessive Bandwidth Use

The Service's bandwidth limitations vary based on the features you use. If we determine your bandwidth usage to be significantly excessive in relation to other users of similar features, we reserve the right to suspend your Account, throttle your file hosting, or otherwise limit your activity until you can reduce your bandwidth consumption. We also reserve the right—after providing advance notice—to delete repositories that we determine to be placing undue strain on our infrastructure. For guidance on acceptable use of object storage in repositories, refer to [AUTOTITLE](/repositories/working-with-files/managing-large-files/about-large-files-on-github). For more details on specific features' bandwidth limitations, see the [GitHub Additional Product Terms](/site-policy/github-terms/github-terms-for-additional-products-and-features).

## 10. Advertising on GitHub

**Short version:** _We do not generally prohibit use of GitHub for advertising. However, we expect our users to follow certain limitations, so GitHub does not become a spam haven. No one wants that._

While we understand that you may want to promote your Content by posting supporters' names or logos in your Account, the primary focus of the Content posted in or through your Account to the Service should not be advertising or promotional marketing. This includes Content posted in or through Pages, Packages, repositories, and all other parts of the Service. You may include static images, links, and promotional text in the README documents or project description sections associated with your Account, but they must be related to the project you are hosting on GitHub. You may not advertise in other Users' Accounts, such as by posting monetized or excessive bulk content in issues.

You may not promote or distribute content or activity that is illegal or otherwise prohibited by our [Terms of Service](/site-policy/github-terms/github-terms-of-service) or [Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies), including excessive automated bulk activity (for example, spamming), get-rich-quick schemes, and misrepresentation or deception related to your promotion.

If you decide to post any promotional materials in your Account, you are solely responsible for complying with all applicable laws and regulations, including without limitation the U.S. Federal Trade Commission's Guidelines on Endorsements and Testimonials. We reserve the right to remove any promotional materials or advertisements that, in our sole discretion, violate any GitHub terms or policies.

## 11. User Protection

<!-- localization update 2026-03-11 - Feedback 1131974 -->
You must not engage in activity that significantly harms other users.

We will interpret our policies and resolve disputes in favor of protecting users as a whole.

---

**Enforcement.** GitHub retains full discretion to [take action](/site-policy/github-terms/github-community-guidelines#what-happens-if-someone-violates-githubs-policies) in response to a violation of these policies, including account suspension, account [termination](/site-policy/github-terms/github-terms-of-service#3-github-may-terminate), or [removal](/site-policy/github-terms/github-terms-of-service#2-github-may-remove-content) of content. Please also see our [Community Guidelines](/site-policy/github-terms/github-community-guidelines) for actions you can take if something or someone offends you.

**Reinstatement and appeal.** If your content or account has been disabled or restricted and you seek reinstatement or wish to appeal, please see our [Appeal and Reinstatement page](/site-policy/acceptable-use-policies/github-appeal-and-reinstatement) for information about the process and use our [Appeal and Reinstatement form](https://support.github.com/contact/reinstatement) to submit a request.

---

# GitHub Active Malware or Exploits

Being part of a community includes not taking advantage of other members of the community. We do not allow anyone to use our platform in direct support of unlawful attacks that cause technical harms, such as using GitHub as a means to deliver malicious executables or as attack infrastructure, for example by organizing denial of service attacks or managing command and control servers. Technical harms means overconsumption of resources, physical damage, downtime, denial of service, or data loss, with no implicit or explicit dual-use purpose prior to the abuse occurring.

  Note that GitHub allows dual-use content and supports the posting of content that is used for research into vulnerabilities, malware, or exploits, as the publication and distribution of such content has educational value and provides a net benefit to the security community. We assume positive intention and use of these projects to promote and drive improvements across the ecosystem.

  In rare cases of very widespread abuse of dual-use content, we may restrict access to that specific instance of the content to disrupt an ongoing unlawful attack or malware campaign that is leveraging the GitHub platform as an exploit or malware CDN. In most of these instances, restriction takes the form of putting the content behind authentication, but may, as an option of last resort, involve disabling access or full removal where this is not possible (e.g. when posted as a gist). We will also contact the project owners about restrictions put in place where possible.

  Restrictions are temporary where feasible, and do not serve the purpose of purging or restricting any specific dual-use content, or copies of that content, from the platform in perpetuity. While we aim to make these rare cases of restriction a collaborative process with project owners, if you do feel your content was unduly restricted, we have an [appeals process](/site-policy/acceptable-use-policies/github-appeal-and-reinstatement) in place.

  To facilitate a path to abuse resolution with project maintainers themselves, prior to escalation to GitHub abuse reports, we recommend, but do not require, that repository owners take the following steps when posting potentially harmful security research content:

* Clearly identify and describe any potentially harmful content in a disclaimer in the project’s README.md file or source code comments.
* Provide a preferred contact method for any 3rd party abuse inquiries through a SECURITY.md file in the repository (e.g. "Please create an issue on this repository for any questions or concerns"). Such a contact method allows 3rd parties to reach out to project maintainers directly and potentially resolve concerns without the need to file abuse reports.

  _GitHub considers the npm registry to be a platform used primarily for installation and run-time use of code, and not for research._

---

# GitHub Community Guidelines

Millions of developers across the world host millions of projects—both open and closed source—on GitHub. We're fortunate to be able to play a part in enabling collaboration across the developer community every day, which is a responsibility we don’t take lightly. Together, we all have the exciting opportunity to make this a community we can be proud of.

Our diverse user base brings different perspectives, ideas, and experiences, and ranges from people who created their first "Hello World" project last week to the most well-known software developers in the world. We are committed to making GitHub an environment that welcomes all the different voices and perspectives our community has to offer, while maintaining a safe place for developers to do their best work.

By outlining what we think a [safe, welcoming, and productive community](https://opensource.guide/building-community/) looks like at GitHub, we hope to help you understand how best to interact and collaborate on our platform in line with our [Terms of Service](/site-policy/github-terms/github-terms-of-service) and [Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies).

We encourage our community members to communicate expectations clearly, [moderate](#what-if-something-or-someone-offends-you) their projects where possible, and [report](https://github.com/contact/report-abuse) any content that may violate our [policies](/site-policy/github-terms/github-terms-of-service). GitHub Staff will investigate any reports of abuse, and may moderate public content on our site that we determine to be in violation of our Terms of Service.

## Maintaining a strong community

The primary purpose of the GitHub community is to collaborate on software projects. We are committed to maintaining a community where users are free to express themselves and challenge one another's ideas, both technical and otherwise. At the same time, it's important that users remain respectful and allow space for others to contribute openly. In order to foster both a safe and productive environment, we encourage our community members to look to these guidelines to inform how they interact on our platform. Below, you’ll find some suggestions for how to have successful interactions as a valued member of the GitHub community.

* **Be welcoming and open-minded** - New users join our community each day. Some are well-established developers, while others are just beginning. Be open to other ideas and experience levels. Make room for opinions other than your own and be welcoming to new collaborators and those just getting started.

* **Be respectful** - Working in a collaborative environment means disagreements may happen. But remember to criticize ideas, not people. Share thoughtful, constructive criticism and be courteous to those you interact with. If you’re unable to engage respectfully, consider taking a step back or using some of our moderation tools to deescalate a tense situation.

* **Be empathetic** - GitHub is a global community with people from a wide variety of backgrounds and perspectives, many of which may not be your own. Try to put yourself in others’ shoes and understand their feelings before you address them. Do your best to help make GitHub a community where others feel safe to make contributions, participate in discussions, and share different ideas.

## What if something or someone offends you?

While some disagreements can be resolved with direct, respectful communication between community members, we understand that is not always the case. We encourage our community to contact GitHub Support through the [GitHub Support portal](https://support.github.com/) when they believe content or activity they’ve encountered violates our policies. However, if you run into something or someone on the site that you find objectionable, here are some ways GitHub enables you to take action:

* **Communicate expectations** - Maintainers can set community-specific guidelines to help users understand how to interact with their projects, for example, in a repository’s README, [CONTRIBUTING file](/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors), or [dedicated code of conduct](/communities/setting-up-your-project-for-healthy-contributions/adding-a-code-of-conduct-to-your-project). You can find additional information on building communities on the [Communities](/communities) page.

* **Moderate Comments** - Users with [write-access privileges](/organizations/managing-user-access-to-your-organizations-repositories/repository-roles-for-an-organization) for a repository can [edit, delete, or hide anyone's comments](/communities/moderating-comments-and-conversations/managing-disruptive-comments) on commits, pull requests, and issues. Anyone with read access to a repository can view a comment's edit history. Comment authors and people with write access to a repository can also delete sensitive information from a [comment's edit history](/communities/moderating-comments-and-conversations/tracking-changes-in-a-comment). Moderating your projects can feel like a big task if there is a lot of activity, but you can [add collaborators](/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-personal-account-settings/permission-levels-for-a-personal-account-repository#collaborator-access-for-a-repository-owned-by-a-personal-account) to assist you in managing your community.

* **Lock Conversations**  - If a discussion in an issue, pull request, or commit gets out of hand, off topic, or violates your project’s code of conduct or GitHub’s policies, owners, collaborators, and anyone else with write access can put a temporary or permanent lock on the conversation. For more information, see [AUTOTITLE](/communities/moderating-comments-and-conversations/locking-conversations).

* **Block Users**  - If you encounter a specific user who you would rather not engage with, you can [block the user from your personal account](/communities/maintaining-your-safety-on-github/blocking-a-user-from-your-personal-account) or [from your organization](/communities/maintaining-your-safety-on-github/blocking-a-user-from-your-organization).

* **Limit Interactions** - If your public project is getting unwanted attention, being trolled, spammed, or otherwise, you have the option of setting [temporary interaction limits](/communities/moderating-comments-and-conversations/limiting-interactions-in-your-repository) to keep certain users from interacting with your repository. You can even set [code review limits](https://github.blog/2021-11-01-github-keeps-getting-better-for-open-source-maintainers/#preventing-drive-by-pull-request-approvals-and-requested-changes) to ensure quality contributions on your projects.

While we are passionate about empowering maintainers to moderate their own projects, please contact {% data variables.contact.contact_support %} if you need additional support in dealing with a situation.

## What happens if someone violates GitHub's policies?

We rely on reports from the community, as well as proactive detection, to help ensure that GitHub is a safe, welcoming, and productive platform for software developers. There are a variety of factors we consider when we’re made aware of behavior or content not in line with GitHub’s policies. However, our policy enforcement and content moderation approach prioritizes our vision to be the home for all developers. This means:

* We optimize for code collaboration. We recognize that code can have multiple uses and we distinguish between how the code is being used on the platform and other possible uses. We also think about how our enforcement actions can affect a potentially complicated web of interdependencies across the platform and aim to restrict as little legitimate content as possible.

* We take a human-centered approach to content moderation and we tailor our responses to meet the needs of a specific situation. Our global team investigates the reports we receive on a case-by-case basis—considering context and the surrounding facts—before taking action. This could include taking into account potentially offensive content being posted in a way that lacks context or makes it easy for other users to unwittingly view or interact with while using GitHub. In those instances, we may favor moderation in order to safeguard our community.

* Our decisions are rooted in our core belief that serving an interconnected community and empowering human progress through developer collaboration requires a commitment to diversity, inclusion, and belonging.

Where we have decided that moderation action is warranted, these are some of the ways we may respond:

* Removing the offending content
* Blocking or disabling the offending content
* Downgrading the visibility of the offending content
* Hiding a user account or organization from public view
* Suspending a user account or organization

## Appeal and Reinstatement

If your content or account has been disabled or restricted and you seek reinstatement or wish to appeal, please see our [Appeal and Reinstatement page](/site-policy/acceptable-use-policies/github-appeal-and-reinstatement) for information about the process and use our [Appeal and Reinstatement form](https://support.github.com/contact/reinstatement) to submit a request.

## Legal Notices

We dedicate these Community Guidelines to the public domain for anyone to use, reuse, adapt, or whatever, under the terms of [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/).

These are only guidelines; they do not modify our [Terms of Service](/site-policy/github-terms/github-terms-of-service) and are not intended to be a complete list. Under those terms, GitHub retains full discretion to remove any content or terminate any accounts for activity that violates our [Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies). These guidelines describe when we will exercise that discretion.

---

# GitHub Terms for Additional Products and Features

Version Effective Date: April 27, 2026

When you use GitHub, you may be given access to lots of additional products and features ("Additional Products and Features"). Because many of the Additional Products and Features offer different functionality, your Agreement with us (the "Agreement") includes the specific terms for that product or feature combined with your main agreement — the GitHub Terms of Service or GitHub Customer Agreement, or the GitHub Corporate Terms of Service or other legacy GitHub contract, or a Microsoft volume licensing agreement. Below, we've listed those products and features, along with the corresponding additional terms that apply to your use of them.

By using the Additional Products and Features, you also agree to the applicable GitHub Terms for Additional Products and Features listed below. A violation of these GitHub Terms for Additional Products and Features is a violation of the Agreement. Capitalized terms not defined here have the meaning given in the Agreement.

**For Enterprise users**
* **GitHub Enterprise Cloud** users may have access to the following Additional Products and Features: Actions, Advanced Security (including Code Security and Secret Protection), Advisory Database, Codespaces, Dependabot, GitHub Enterprise Importer, Packages, and Pages.

* **GitHub Enterprise Server** users may have access to the following Additional Products and Features: Actions, Advanced Security (including Code Security and Secret Protection), Advisory Database, Connect, Dependabot, GitHub Enterprise Importer, Packages, Pages, and SQL Server Images.

## Actions

GitHub Actions enables you to create custom software development lifecycle workflows directly in your GitHub repository. Actions is billed on a usage basis. The [Actions documentation](/actions) includes details, including compute and storage quantities (depending on your Account plan), and how to monitor your Actions minutes usage and set usage limits.

Actions and any elements of the Actions product or service may not be used in violation of the Agreement, the [GitHub Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies), or the GitHub Actions service limitations set forth in the [Actions documentation](/actions/learn-github-actions/usage-limits-billing-and-administration). Additionally, regardless of whether an Action is using self-hosted runners, Actions should not be used for:
* Cryptomining;
* Disrupting, gaining, or attempting to gain unauthorized access to, any service, device, data, account, or network (other than those authorized by the [GitHub Bug Bounty program](https://bounty.github.com));
* The provision of a stand-alone or integrated application or service offering the Actions product or service, or any elements of the Actions product or service, for commercial purposes;
* Any activity that places a burden on our servers, where that burden is disproportionate to the benefits provided to users (for example, don't use Actions as a content delivery network or as part of a serverless application, but a low benefit Action could be ok if it’s also low burden); or
* If using GitHub-hosted runners, any other activity unrelated to the production, testing, deployment, or publication of the software project associated with the repository where GitHub Actions are used.

In order to prevent violations of these limitations and abuse of GitHub Actions, GitHub may monitor your use of GitHub Actions. Misuse of GitHub Actions may result in termination of jobs, restrictions in your ability to use GitHub Actions, disabling of repositories created to run Actions in a way that violates these Terms, or in some cases, suspension or termination of your GitHub account.

_Use for Development and Testing_

You may only access and use GitHub Actions to develop and test your application(s). Only one licensed user may access a virtual machine provided by Actions at any time.

_Authorized Developer_

You appoint GitHub as your authorized developer with respect to Apple software included in Actions. GitHub is responsible for complying with the terms for any such software included in Actions and will keep confidential any confidential information of Apple accessed as part of Actions.

_Third Party Repository Service Access_

If you grant GitHub access to your third-party repository service account(s), you authorize GitHub to scan the account(s), including the contents of your Public and Private Repositories, for purposes of providing GitHub Actions.

_Self-Hosted Runners on GitHub Actions_

If you use self-hosted runners, you have the ability to turn off automatic updates but GitHub reserves the right to override your choice for critical security updates.

## Advanced Security

GitHub makes extra security features available to customers under Advanced Security licenses. From April 1, 2025, features that were previously only available under a single GitHub Advanced Security license will be alternatively available under two separate licenses: GitHub Code Security (code scanning and dependency scanning features) and GitHub Secret Protection (secret scanning features).  The [Advanced Security documentation](/get-started/learning-about-github/about-github-advanced-security) provides more details.

Advanced Security features are licensed on a "Unique Committer" basis. A "Unique Committer" is a licensed user of GitHub Team, GitHub Enterprise, GitHub Enterprise Cloud, or GitHub Enterprise Server, who has made a commit in the last 90 days to any repository with any GitHub Advanced Security functionality activated. You must acquire an appropriate GitHub Advanced Security User license for each of your Unique Committers. You may only use GitHub Advanced Security features on codebases that are developed by or for you. For GitHub Team and GitHub Enterprise Cloud users, some Advanced Security features may also require the use of GitHub Actions.

For secret scanning with GitHub Advanced Security or GitHub Secret Protection, when you opt-in to automatic validity checks for partner patterns, exposed third-party tokens may be shared with the relevant partner, in order to provide you with more information about the validity of the token. Not all partners are based in the United States. The [Secret scanning patterns documentation](/enterprise-cloud@latest/code-security/secret-scanning/introduction/supported-secret-scanning-patterns) provides more details on which partners support the validity check.

## Advisory Database

The GitHub Advisory Database allows you to browse or search for vulnerabilities that affect open source projects on GitHub.

_License Grant to Us_

We need the legal right to submit your contributions to the GitHub Advisory Database into public domain datasets such as the [National Vulnerability Database](https://nvd.nist.gov/) and to license the GitHub Advisory Database under open terms for use by security researchers, the open source community, industry, and the public. You agree to release your contributions to the GitHub Advisory Database under the [Creative Commons Zero license](https://creativecommons.org/publicdomain/zero/1.0/).

_License to the GitHub Advisory Database_

The GitHub Advisory Database is licensed under the [Creative Commons Attribution 4.0 license](https://creativecommons.org/licenses/by/4.0/). The attribution term may be fulfilled by linking to the GitHub Advisory Database at <https://github.com/advisories> or to individual GitHub Advisory Database records used, prefixed by <https://github.com/advisories>.

## Codespaces

_Note: The github.dev service, available by pressing . on a repo or navigating directly to github.dev, is governed by GitHub's Beta Terms of service._

GitHub Codespaces enables you to develop code directly from your browser using the code within your GitHub repository. Codespaces and any elements of the Codespaces service may not be used in violation of the Agreement or the Acceptable Use Policies. Additionally, Codespaces should not be used for:
* Cryptomining;
* Using our servers to disrupt, or to gain or to attempt to gain unauthorized access to any service, device, data, account or network (other than those authorized by the GitHub Bug Bounty program);
* The provision of a stand-alone or integrated application or service offering Codespaces or any elements of Codespaces for commercial purposes;
* Any activity that places a burden on our servers, where that burden is disproportionate to the benefits provided to users (for example, don't use Codespaces as a content delivery network, as part of a serverless application, or to host any kind of production-facing application); or
* Any other activity unrelated to the development or testing of the software project associated with the repository where GitHub Codespaces is initiated.

In order to prevent violations of these limitations and abuse of GitHub Codespaces, GitHub may monitor your use of GitHub Codespaces. Misuse of GitHub Codespaces may result in termination of your access to Codespaces, restrictions in your ability to use GitHub Codespaces, or the disabling of repositories created to run Codespaces in a way that violates these Terms.

Codespaces allows you to load extensions from the Microsoft Visual Studio Marketplace (“Marketplace Extensions”) for use in your development environment, for example, to process the programming languages that your code is written in. Marketplace Extensions are licensed under their own separate terms of use as noted in the Visual Studio Marketplace, and the terms of use located at https://aka.ms/vsmarketplace-ToU. GitHub makes no warranties of any kind in relation to Marketplace Extensions and is not liable for actions of third-party authors of Marketplace Extensions that are granted access to Your Content. Codespaces also allows you to load software into your environment through devcontainer features. Such software is provided under the separate terms of use accompanying it. Your use of any third-party applications is at your sole risk.

The generally available version of Codespaces is not currently available for U.S. government customers. U.S. government customers may continue to use the Codespaces Beta Preview under separate terms. See [Beta Preview terms](/site-policy/github-terms/github-terms-of-service#k-beta-previews).

## Competitive Benchmarking

If you offer a product or service competitive to any GitHub product or service, by using that GitHub product or service, you agree to and hereby waive any restrictions as to GitHub on competitive use and benchmark testing in the terms governing your competitive product or service. If you do not intend to waive such restrictions in your terms of use, you are not allowed to use that GitHub product or service.

## Connect

With GitHub Connect, you can share certain features and data between your GitHub Enterprise Server deployment and your GitHub Enterprise Cloud organization or enterprise account on GitHub.com. In order to enable GitHub Connect, you must have at least one (1) account on GitHub Enterprise Cloud or GitHub.com, and one (1) licensed deployment of GitHub Enterprise Server. Your use of GitHub Enterprise Cloud or GitHub.com through Connect is governed by the terms under which you license GitHub Enterprise Cloud or GitHub.com. Use of Personal Data is governed by the [GitHub Privacy Statement](/site-policy/privacy-policies/github-privacy-statement).

## GitHub Copilot

For GitHub Copilot Business and Copilot Enterprise license holders, your use of GitHub Copilot is governed by the [GitHub Copilot Product Specific Terms](https://github.com/customer-terms/github-copilot-product-specific-terms).

For all other GitHub Copilot users, your use of GitHub Copilot is governed by [Section J (AI Features) of the GitHub Terms of Service](/site-policy/github-terms/github-terms-of-service#j-ai-features-training-and-your-data).

## GitHub Enterprise Importer

Importer is a framework for exporting data from other sources to be imported to the GitHub platform. Importer is provided “AS-IS”.

## npm

npm is a software package hosting service that allows you to host your software packages privately or publicly and use packages as dependencies in your projects. npm is the registry of record for the JavaScript ecosystem. The npm public registry is free to use but customers are billed if they want to publish private packages or manage private packages using teams. The [npm documentation](https://docs.npmjs.com/) includes details about the limitation of account types and how to manage [private packages](https://docs.npmjs.com/about-private-packages) and [organizations](https://docs.npmjs.com/organizations). Acceptable use of the npm registry is outlined in the [open-source terms](https://www.npmjs.com/policies/open-source-terms). There are supplementary terms for both the npm [solo](https://www.npmjs.com/policies/solo-plan) and [org](https://www.npmjs.com/policies/orgs-plan) plans. The npm [Terms of Use](https://www.npmjs.com/policies/terms) apply to your use of npm.

## Packages

GitHub Packages is a software package hosting service that allows you to host your software packages privately or publicly and use packages as dependencies in your projects. GitHub Packages is billed on a usage basis. The [Packages documentation](/packages/learn-github-packages/introduction-to-github-packages) includes details, including bandwidth and storage quantities (depending on your Account plan), and how to monitor your Packages usage and set usage limits. Packages bandwidth usage is limited by the [GitHub Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies).

## Pages

Each Account comes with access to the [GitHub Pages static hosting service](/pages/getting-started-with-github-pages/about-github-pages). GitHub Pages is intended to host static web pages, but primarily as a showcase for personal and organizational projects.

GitHub Pages is not intended for or allowed to be used as a free web hosting service to run your online business, e-commerce site, or any other website that is primarily directed at either facilitating commercial transactions or providing commercial software as a service (SaaS). Some monetization efforts are permitted on Pages, such as donation buttons and crowdfunding links.

_Bandwidth and Usage Limits_

GitHub Pages are subject to some specific bandwidth and usage limits, and may not be appropriate for some high-bandwidth uses. Please see our [GitHub Pages limits](/pages/getting-started-with-github-pages/about-github-pages) for more information.

_Prohibited Uses_

GitHub Pages may not be used in violation of the Agreement, the GitHub [Acceptable Use Policies](/site-policy/acceptable-use-policies/github-acceptable-use-policies), or the GitHub Pages service limitations set forth in the [Pages documentation](/pages/getting-started-with-github-pages/about-github-pages#guidelines-for-using-github-pages).

If you have questions about whether your use or intended use falls into these categories, please contact us through the [GitHub Support portal](https://support.github.com/). GitHub reserves the right at all times to reclaim any GitHub subdomain without liability.

_Educational Exercises_

Using GitHub Pages to create a copy of an existing website as a learning exercise is not prohibited. However, you must write the code yourself, the site must not collect any user data, and you must include a prominent disclaimer on the site indicating that the project is not associated with the original and was only created for educational purposes.

## Previews

Previews means software, online services and additional products and features provided for preview, evaluation, demonstration or trial purposes, or pre-release versions of those, such as alpha, beta, or early access. If your Agreement does not include terms and conditions that address Previews, then the following terms apply. GitHub grants a limited right to use a non-production instance of the Preview. Previews are provided “AS-IS”, “WITH ALL FAULTS” and “AS AVAILABLE”. GitHub may change or discontinue Previews at any time without notice. Any information we give you about a private Preview will be considered GitHub’s confidential information. If you choose to provide comments or suggestions about a Preview, we may use that feedback for any purpose without obligation of any kind. GitHub’s maximum liability is limited to direct damages up to US $500. GitHub has no obligation to defend, indemnify, or hold you harmless for claims brought by third parties arising from your use of Previews.

## Sponsors Program

GitHub Sponsors allows the developer community to financially support the people and organizations who design, build, and maintain the open source projects they depend on, directly on GitHub. In order to become a Sponsored Developer, you must agree to the [GitHub Sponsors Program Additional Terms](/site-policy/github-terms/github-sponsors-additional-terms).

## SQL Server Images

You may download Microsoft SQL Server Standard Edition container image for Linux files ("SQL Server Images"). You must uninstall the SQL Server Images when your right to use the Software ends. Microsoft Corporation may disable SQL Server Images at any time.

## GitHub Models

GitHub Models is a feature that allows you to learn, try, and test artificial intelligence models on GitHub.com. You can access GitHub Models via the [GitHub Marketplace](https://github.com/marketplace). Learn more about GitHub Models by visiting [Prototyping with AI models](/github-models/prototyping-with-ai-models).

Your use of this feature is subject to the terms of the company hosting the model and the model license.
