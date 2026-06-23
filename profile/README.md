<p align="center">
  <img src="https://raw.githubusercontent.com/Raven-Scout/scout-plugin/main/docs/assets/og.png" alt="Scout" width="100%">
</p>

<h1 align="center">Scout</h1>

<p align="center">
  <strong>An autonomous daily briefing that cross-checks all your work tools —<br>so nothing falls through the cracks, and you can trust what it surfaces.</strong>
</p>

---

Scout runs unattended as scheduled [Claude Code](https://claude.com/claude-code) sessions. It reads Slack, Calendar, Gmail, Linear, GitHub, and meeting transcripts; cross-checks every finding against the others; and each morning hands you a short list of what actually needs you — every item tagged by how many sources confirm it.

What you get is a persistent, interlinked knowledge base you can browse in Obsidian, a daily action list you can trust *because you can see its work*, and native apps on every device that read and write that same vault.

## Why Scout is different

- **It cross-checks.** No single tool is the source of truth — a calendar invite is verified against the transcript, a Linear ticket against the PR. Single-source claims are flagged, not asserted.
- **It shows its confidence.** Every entry is tagged `verified` / `single-source` / `unverified` / `stale` / `contradicted`, so you always know how much weight to give it.
- **It's structured.** A formal, ontology-validated knowledge graph of typed people, projects, and tasks — not a flat pile of notes.
- **It improves itself.** A nightly *Dreaming* session logs its own mistakes, rewrites its instructions, and works down a self-managed wishlist — every change a reviewable, revertible git commit.

## The repositories

Scout is one engine with several surfaces. Start with the plugin; add whichever apps fit your devices.

| Repo | What it is | Stack |
| --- | --- | --- |
| **[scout-plugin](https://github.com/Raven-Scout/scout-plugin)** | **The engine — start here.** The Claude Code plugin that runs the scheduled sessions, cross-checks your connectors, and maintains the vault at `~/Scout/`. | Python |
| **[Scout](https://github.com/Raven-Scout/Scout)** | **macOS app** — the daily driver. Control Center, an Action Items board, and a full editor for your launchd schedule. | Swift |
| **[scout-iOS-app](https://github.com/Raven-Scout/scout-iOS-app)** | **iPhone app** — reads the vault over iCloud/Obsidian: render today's briefing, mark items done, browse the knowledge base with tappable `[[wikilinks]]`. | Swift |
| **[scout-android](https://github.com/Raven-Scout/scout-android)** | **Android app + connector** — action items on your phone, plus notification capture that feeds your phone's activity back into Scout. | Kotlin |

## How the pieces fit together

```
          ┌────────────────────────────────────────────┐
          │  scout-plugin  (the scheduled brain)         │
          │  Claude Code sessions → cross-check →         │
          │  write a plain-markdown vault at ~/Scout/     │
          └───────────────────────┬──────────────────────┘
                                  │  markdown + logs  (the vault)
       ┌───────────────────────────┼───────────────────────────┐
       ▼                           ▼                           ▼
  Scout (macOS)            scout-iOS-app              scout-android
  daily driver            read via iCloud            read + notif. connector
```

The **plugin is canonical** — it produces a plain-markdown vault, and every app is a wrapper that reads and writes that same vault, so the markdown always stays the source of truth. A shared parser contract (`parser-corpus.json`) is verified byte-for-byte across the plugin, the macOS app, and the iOS app, so all three agree on exactly how an action-items file is read.

## Getting started

```bash
# 1. Install the engine
curl -fsSL https://raw.githubusercontent.com/Raven-Scout/scout-plugin/main/install.sh | bash

# 2. In Claude Code, create your vault
/scout-setup
```

That's the whole system. The native apps are optional surfaces on top — see each repo's README for build and install instructions.

---

<p align="center">
  <a href="https://raven-scout.github.io/scout-plugin/privacy.html">Privacy</a> ·
  <a href="https://raven-scout.github.io/scout-plugin/terms.html">Terms</a> ·
  <a href="https://github.com/Raven-Scout/.github/blob/main/SECURITY.md">Security</a> ·
  <a href="https://github.com/Raven-Scout/.github/blob/main/CODE_OF_CONDUCT.md">Code of Conduct</a>
</p>

<p align="center"><sub>Scout is an independent open-source project, not affiliated with Anthropic, Microsoft, or Keboola. Built on <a href="https://claude.com/claude-code">Claude Code</a>.</sub></p>
