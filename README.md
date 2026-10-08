# AEmbers

**Data extraction infrastructure, anti-bot work, and agent tooling.**

I build the layer *below* the HTTP request — the part that decides whether a crawl survives a
week or dies in an hour. Proxy and identity rotation, challenge handling, protocol
reconstruction, and the plumbing that keeps long-running autonomous systems from falling over.

---

## Public work

| Repository | What it is |
|---|---|
| **[sophialin-stage-compact](https://github.com/AEmbers/sophialin-stage-compact)** | A stage-aware context compaction proxy for coding agents. A rework of `billion-context`: compaction fires when a *stage* resolves rather than when a token percentage trips, so a single session can run for weeks. TypeScript, full English / 中文 documentation. |
| **[dsh-adjudication](https://github.com/AEmbers/dsh-adjudication)** | A multi-domain adjudication engine: a deterministic pipeline (gate → bundle → anchor → critique) plus a registry of pluggable domain packs, with an LLM step inside the pipeline rather than around it. Ported from Alibaba's `open-code-review`; per-file derivation is documented in `NOTICE`. |
| **[dsh-source-patch](https://github.com/AEmbers/dsh-source-patch)** | Anchored binary patching for a *packaged* Electron application. Lists, verifies, applies and reverts patches against `resources/app.asar` — every anchor must match exactly once, the original is backed up, and the result is read back and compared before the patch is accepted. |

## What I work on

- **Extraction at scale** — proxy pools, per-session identity, block detection, retry ladders, resumable crawls that run unattended instead of supervised.
- **Anti-bot** — challenge flows, TLS / JA3 fingerprints, headless detection, CAPTCHA- and MFA-gated paths.
- **Protocol-level reverse engineering** — client/server protocol reconstruction, binary and packed formats, traffic analysis.
- **Agent and LLM infrastructure** — tool-calling plumbing, deterministic pipelines with model calls embedded in them, and context management for long-lived sessions.

## Stack

`Python` · `TypeScript / Node.js` · `Shell` · `SQL` · `Linux` · `Docker`

Most of my recent work is on **DeepSeek Harness (dsh)** — a plugin-based agent host — where I write
the extensions and the low-level plumbing they need.
