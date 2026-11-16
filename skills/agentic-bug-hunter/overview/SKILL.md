---
name: agentic-bug-hunter
description: "AwareXone Agentic-Bug-Hunter skills — full bug bounty hunting workflow (Web2 + Web3): recon, vuln classes, bug chaining, triage/validation, report writing, LLM red-teaming, token audits, and more. Use when Jesse asks about Agentic-Bug-Hunter, bug bounty hunting, or wants to hunt/audit a target."
---

# Agentic-Bug-Hunter Skills

Source: https://github.com/awarexone/Agentic-Bug-Hunter (MIT, 5,917
stars, 1,065 forks, actively maintained — last push 2026-11-12).
Saved 2026-11-16 at Jesse's request — the 25 skills only, verbatim,
with their original names, in the custom-skills folders (both
`~/workspace/custom-skills/` and `~/.agents/skills/`).

**NOT installed:** the `bughunter` CLI, the MCP servers, and the
external recon tools (subfinder, httpx, nuclei, katana, ffuf, nmap)
were deliberately NOT installed — Jesse chose "skill-nya aja". The
CLI would need a pip/uv install + an AI provider (Ollama local or a
Groq free-tier key); ask Jesse before installing it.

The repo root's master workflow (`SKILL.md`, 1,223 lines) is kept here
as `MASTER-WORKFLOW.md` for reference. The 9 agent definitions from
`bughunter/agents/` are kept here under `agents/` as reference
prompts — they are NOT wired into Muse.

## The 25 skills

| Skill | What it does |
|---|---|
| `bug-bounty` | Master workflow: Recon → Learn → Hunt → Validate → Report. 26 Web2 + 10 Web3 vuln classes, A→B bug chaining, bypass tables, language-specific grep, reporting (7-Question Gate, CVSS 3.1). |
| `bb-methodology` | 5-phase non-linear hunting methodology, developer psychology, session discipline, tool routing by phase, Wide/Deep route selection. |
| `web2-recon` | Recon: subdomain enum, asset discovery, fingerprinting, HackerOne scope. |
| `web2-vuln-classes` | Web2 vulnerability classes in depth. |
| `web3-audit` | Smart contract audit (10 classes, Foundry PoC template). Overlaps the `web3-*` hunting skills — this is the Agentic-Bug-Hunter version. |
| `bug-chaining` | Chain bug A → B → C for 3–10x payout. |
| `triage-validation` | 7-Question Gate + 4 validation gates — kill weak findings before reporting. |
| `report-writing` | H1 / Bugcrowd / Intigriti / Immunefi report format, human tone, CVSS. |
| `bugcrowd-reporting` | Bugcrowd-specific reporting. |
| `graphql-audit` | GraphQL audit (auth bypass, introspection, batching). |
| `llm-redteam` | LLM/AI security testing: prompt injection, jailbreak, exfil, system prompt extraction, ASI01–ASI10. |
| `meme-coin-audit` | Token/rug-pull audit (mint authority, LP lock, honeypot, bonding curve). |
| `mcp-server-audit` | Auditing MCP servers. |
| `mobile-pentest` | Mobile app pentesting. |
| `cloud-pentest` | Cloud/infra pentesting (S3, Azure, GCP, origin IPs). |
| `cicd-security` | CI/CD pipeline security. |
| `credential-attack` | Credential attacks (wordlists, OSINT, breach check — stops before live spraying without human go/no-go). |
| `client-reverse` | Client-side reverse engineering. |
| `jsmax` | JavaScript analysis (prototype pollution, sinks, source maps). |
| `pii-hunter` | PII discovery. |
| `security-arsenal` | Tool arsenal reference. |
| `agentic-app-audit` | Auditing agentic apps. |
| `argus` | (See its SKILL.md for its specific scope.) |
| `johnwick` | (See its SKILL.md for its specific scope.) |
| `omni-killchain` | Full kill-chain methodology. |

## The golden rule (from the master workflow)

> "Can an attacker do this RIGHT NOW against a real user who has taken
> NO unusual actions — and does it cause real harm (stolen money,
> leaked PII, account takeover, code execution)?" If the answer is NO —
> STOP. Do not write. Do not explore further.

## Scope rule

Only hunt targets with an active bug bounty program, and only in-scope
assets. Verify scope first (`/scope` in the CLI, or the program's
scope page). Unauthorized testing is illegal — the scope check is the
hunter's responsibility, not the tool's.
