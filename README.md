# Bug bounty skills

A collection of skills for learning bug bounty hunting, gathered from open-source repos and put in one place with notes on the recon tools that go with them. It is a library and a set of notes, not a scanner and not a submit button.

## What is inside

939 skills, in eight groups:

- skills/anthropic-cybersecurity/ holds 818 structured cybersecurity skills across 29 domains, mapped to MITRE ATT&CK, NIST CSF 2.0, MITRE ATLAS, D3FEND, NIST AI RMF, and MITRE F3. This is the reference shelf. When a hunt touches a specific domain, the playbook for it is usually already written here.
- skills/claude-bughunter/ holds 82 skills for bug hunting and external red-team work, with 681 disclosed-report patterns across 24 vulnerability classes, plus an overview folder with the usage guide. This is the set to reach for first when hunting.
- skills/agentic-bug-hunter/ holds 25 skills for the end-to-end workflow, from recon to report, plus an overview folder with the master workflow. This is the set that ties the rest together.
- skills/strix/ holds 9 skills for web, API, code, and OWASP testing, plus CI scanning and fixing.
- skills/shannon/ holds 1 pointer skill for the Shannon autonomous pentester, with its reference docs.
- skills/osmedeus-expert/ holds 1 skill for driving the Osmedeus recon engine.
- skills/securitytesting/ holds 1 skill: the web-application hunting checklist from The-XSS-Rat/SecurityTesting, 18 sections from strategy and recon through XSS, SQLi, SSRF, and chaining. Use it to plan coverage before a hunt.
- skills/bitsec/ holds 2 skills from Bitsec-AI: web3-audit-corpus, the open dataset of 12,767 public audits and 175,640 findings (2015–2026) to use as a reference library before a hunt, and scabench, the benchmark for scoring AI audit agents on 31 real contest projects with the Nethermind AuditAgent scoring algorithm. The Bittensor and subnet repos from the same org were skipped.

The tools/ folder has a short note per recon tool that was verified working: amass, subfinder, httpx, bbot, spiderfoot, theHarvester, WhatWeb, osmedeus, and OneForAll. No tool code is vendored here. The frameworks/ folder has a short note per framework that was not installed, with the blocker written down: pentagi, PentestGPT, DeepAudit, rengine, reconftw, Strix, and Shannon.

Every skill folder keeps its own license file and an audit verdict file from the review done when the skills were saved. The verdicts say what was checked and what to be careful about.

## How to use it

Start with docs/pipeline.md. It walks the phases in order: quiet recon, fingerprinting, hunting, validating, reporting. Pick a skill by phase, not by name. Run the recon tools first and read what they return before touching anything else.

The rules that matter most are short. Only test targets you are authorized to test, inside a published program scope. A finding without a reproduction is a note, not a report. Nothing here files a report for you; reports go through your own account on the bounty platform.

## Sources

Nine of the upstream repos are forked under the same account, as source references. The other thirteen are still waiting: GitHub throttles fork creation after a burst of forks, so those will be forked once the limit lifts. The skills themselves are already in this repo either way.

Forked so far:

- github.com/Jesseliverse01/strix (usestrix/strix)
- github.com/Jesseliverse01/shannon (KeygraphHQ/shannon)
- github.com/Jesseliverse01/Anthropic-Cybersecurity-Skills (mukul975/Anthropic-Cybersecurity-Skills)
- github.com/Jesseliverse01/pentagi (vxcontrol/pentagi)
- github.com/Jesseliverse01/PentestGPT (GreyDGL/PentestGPT)
- github.com/Jesseliverse01/DeepAudit (lintsinghua/DeepAudit)
- github.com/Jesseliverse01/Agentic-Bug-Hunter (awarexone/Agentic-Bug-Hunter)
- github.com/Jesseliverse01/Claude-BugHunter (elementalsouls/Claude-BugHunter)
- github.com/Jesseliverse01/spiderfoot (smicallef/spiderfoot)

Still to fork, once GitHub lifts the limit:

- laramies/theHarvester
- owasp-amass/amass
- projectdiscovery/subfinder
- blacklanternsecurity/bbot
- projectdiscovery/httpx
- shmilylty/OneForAll
- yogeshojha/rengine
- six2dez/reconftw
- urbanadventurer/WhatWeb
- j3ssie/osmedeus
- The-XSS-Rat/SecurityTesting
- Bitsec-AI/web3-audit-corpus
- Bitsec-AI/scabench

## Licensing

The writing in this repo is MIT, and it covers only that writing. Each skill keeps its own license, listed in LICENSES.md. No AGPL or GPL code is vendored here.
