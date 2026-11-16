---
name: claude-bughunter
description: Claude-BugHunter skill bundle (elementalsouls/Claude-BugHunter, MIT code / CC BY 4.0 content, 7,120 stars) — 82 hunting + methodology skills across 24 vulnerability classes, built from 681 disclosed bug-bounty reports, plus a Python CLI (cbh) with recon, surface, classify, triage, and report commands (HackerOne / Bugcrowd / Intigriti / Immunefi templates). Use for authorized bug-bounty hunting only — in-scope targets, with the program's authorization. Never test outside scope.
---

# Claude-BugHunter — overview

A skill bundle for bug hunting and external red-team work. 82 skills, 15 slash
commands, 681 disclosed-report patterns across 24 core vulnerability classes,
plus enterprise identity + infrastructure attack matrices. Code is MIT,
skill content is CC BY 4.0 (see LICENSE + LICENSE-CONTENT + NOTICE).

## The skills (all saved here with a `cbh-` prefix)

The bare names already existed in this collection from other authors (8 of 9
overlaps are different content; `bugcrowd-reporting` was byte-identical and was
not duplicated). Frontmatter names inside the files stay bare; the folder name
is the disambiguator.

- **Master workflow:** `cbh-bug-bounty` (recon → scope → research → testing →
  validation → reporting, HackerOne scope first), `cbh-bb-methodology`,
  `cbh-bb-local-toolkit` (local tool + wordlist paths), `cbh-recon-scope-triage`,
  `cbh-triage-validation` (7-Question Gate), `cbh-report-writing`,
  `cbh-redteam-report-template`, `cbh-evidence-hygiene`, `cbh-security-arsenal`.
- **Hunting skills (`cbh-hunt-*`, one per class, each built from disclosed
  reports):** xss (174 reports), sqli, ssrf, idor, csrf, cors, ssti, xxe, lfi,
  rce, jwt-crypto, oauth, saml, graphql, grpc, websocket, nosqli, deserialization,
  file-upload, race-condition, business-logic, auth-bypass, mfa-bypass,
  forgot-password, session, host-header, open-redirect, clickjacking,
  cache-poison, http-smuggling, subdomain, api-misconfig, shadow-api, spa-api,
  source-leak, llm-ai, rag-vector, fintech-graphql, captcha-bypass,
  brute-force, ato, dom, html-injection, exceptional-conditions, misc, and
  framework hunts (aspnet, laravel, nextjs, nodejs, springboot).
- **Infra + cloud + identity:** `cbh-cloud-iam-deep`, `cbh-hunt-cloud-misconfig`,
  `cbh-hunt-k8s`, `cbh-hunt-cicd`, `cbh-m365-entra-attack`, `cbh-okta-attack`,
  `cbh-enterprise-vpn-attack`, `cbh-vmware-vcenter-attack`, `cbh-hunt-ldap`,
  `cbh-hunt-ntlm-info`, `cbh-hunt-sharepoint`, `cbh-hunt-tls-network`,
  `cbh-supply-chain-attack-recon`, `cbh-offensive-osint`, `cbh-osint-methodology`.
- **Pipelines:** `cbh-apk-redteam-pipeline`, `cbh-ios-redteam-pipeline`,
  `cbh-redteam-mindset`, `cbh-mid-engagement-ir-detection`.
- **Web3:** `cbh-web3-audit`, `cbh-meme-coin-audit` (different content from the
  existing `web3-audit` / `meme-coin-audit` skills).

## The CLI (`cbh`, Python 3.9+, stdlib + optional `requests`)

Kept in the repo clone at `~/workspace/claude-bughunter-repo/` — not installed,
skills only. Five subcommands compose the engagement loop:

- `cbh recon <target>` — passive subdomain enum + live-host probe + URL
  classification; writes `recon/<target>/` incl. `manifest.json`.
- `cbh surface <target>` — ranked P1/P2/Kill attack surface from the manifest.
- `cbh classify <url>` — match one URL against hunt-skill descriptions.
- `cbh triage <finding.md>` — the 7-Question Gate: PASS / DOWNGRADE / KILL.
- `cbh report <finding.md>` — report draft in HackerOne / Bugcrowd / Intigriti /
  Immunefi templates.

Modes: curl-only (just Python), Burp proxy (`cbh --burp`, Burp Suite
Pro/Community), or Burp MCP (Pro + MCP extension + Claude Code). `subfinder`
improves subdomain enum; without it, recon falls back to crt.sh alone.

## Bug-bounty submission — how it works with Muse

Muse can run the whole workflow: pick an in-scope program, recon, hunt with
the matching `cbh-hunt-*` skill, validate with the 7-Question Gate, and draft
the report in the platform's template. The actual submission goes through the
reporter's own platform account (HackerOne, Bugcrowd, Intigriti, Immunefi) —
payout, identity, and safe harbor are tied to that account. Muse can submit
via the browser from the user's logged-in session when asked, or hand over a
ready draft. What Muse never does: test a target outside the program's scope,
or test without the program's authorization. Only in-scope programs, always.

## Rules

- Only hunt in-scope bounty programs. Unauthorized testing is illegal.
- A skill is a procedure, not permission: every live test needs the program's
  authorization for that exact target.
- Never paste a private key, seed, or platform API token in chat. Credentials
  live in the platform account / local env, never in a skill file.
- The repo does NOT redistribute upstream community skills directly — some
  skills are install recipes pointing at their original sources (see
  `docs/credits.md` in the clone).

## Available connectors

- [HackenProof](~/workspace/custom-connectors/custom.hackenproof/CONNECTOR.md) — Bugcrowd-style bounty platform API (Bearer token). Connected 2026-11-16; API host unreachable from the Muse network that day, website route works.
