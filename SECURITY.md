# Security Policy

This policy applies to all repositories in the [Raven Scout](https://github.com/Raven-Scout)
organization — the Scout Claude Code plugin and the macOS, iOS, and Android apps.

## Supported versions

Scout is an actively developed open-source project. Security fixes are made against the latest
released version and the `main` branch of each repository. We do not backport fixes to older
versions; please update to the latest version before reporting.

## Reporting a vulnerability

**Please do not report security vulnerabilities through public GitHub issues, pull requests, or
discussions.**

Instead, report them privately through GitHub's built-in private vulnerability reporting:

1. Go to the affected repository (for example,
   [scout-plugin](https://github.com/Raven-Scout/scout-plugin)).
2. Open the **Security** tab → **Report a vulnerability**, or go directly to the repository's
   **Security Advisories** page and choose **Report a vulnerability**.
3. Describe the issue with enough detail for us to reproduce it.

If you are unsure which repository is affected, report it on
[scout-plugin](https://github.com/Raven-Scout/scout-plugin/security/advisories) and we will route
it.

A helpful report includes:

- the repository and version (or commit) affected;
- the type of issue and the component involved;
- step-by-step instructions to reproduce it;
- the potential impact; and
- any proof-of-concept, logs, or configuration needed to reproduce it.

## What to expect

Scout is maintained by volunteers, so responses are best-effort rather than bound by a service
level agreement. We aim to acknowledge a report within a few days, confirm the issue, and keep you
updated as we work on a fix. We will credit reporters who wish to be named once a fix is released.
Please give us a reasonable opportunity to address an issue before disclosing it publicly.

## Scope and the things you control

Scout is **local-first**: it runs on your own machine, under your own accounts and credentials,
and stores everything in local files and your own git history. Because of that, a large part of
the real security surface is in your hands:

- **Protect your machine and your credentials.** Anyone with access to your computer or your
  connector tokens can access what Scout can access.
- **Keep your vault private.** By default the Scout vault lives in local files and your own git
  history; if you push that history to a remote, treat it as you would any repository that may
  contain sensitive notes, and avoid committing secrets.
- **Keep Scout and Claude Code up to date** so you receive the latest fixes.

Reports about how Scout itself handles credentials, data, or third-party integrations are very
welcome through the private reporting process above.
