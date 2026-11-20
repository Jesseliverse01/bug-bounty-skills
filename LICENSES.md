# Licenses

This repo mixes original writing with skills written by other people. The licenses are not one thing, so this file says plainly what covers what.

## The repo's own writing

The MIT license in LICENSE covers only the original content written for this repo: README.md, SOUL.md, docs/pipeline.md, the notes in tools/ and frameworks/, and the file layout itself. Nothing else.

## The bundled skills

Every skill keeps the license it came with. The license file inside each skill folder is the one that applies to that skill.

- skills/anthropic-cybersecurity/: 818 skills, Apache License 2.0. Source: mukul975/Anthropic-Cybersecurity-Skills.
- skills/strix/: 9 skills, Apache License 2.0. Source: usestrix/strix.
- skills/shannon/: 1 pointer skill plus reference docs, AGPL-3.0 upstream. Source: KeygraphHQ/shannon.
- skills/osmedeus-expert/: 1 skill, MIT. Source: j3ssie/osmedeus.
- skills/agentic-bug-hunter/: 25 skills, MIT. Source: awarexone/Agentic-Bug-Hunter.
- skills/claude-bughunter/: 82 skills, MIT code and CC BY 4.0 skill content. Source: elementalsouls/Claude-BugHunter.
- skills/securitytesting/: 1 skill, no license file upstream — the repo states no license, so the checklist is reproduced here with attribution and is not relicensed. Source: The-XSS-Rat/SecurityTesting.
- skills/bitsec/: 2 skills. web3-audit-corpus: derived metadata and annotations CC BY 4.0 (attribution to Dickson Wu); quoted finding text remains the publishers' copyright. scabench: MIT. Sources: Bitsec-AI/web3-audit-corpus, Bitsec-AI/scabench.

No skill was relicensed. Nothing in those folders was rewritten; the files are verbatim copies of the saved versions, including their own license files. Three example credentials found in the Anthropic bundle were redacted in the saved copies before they were placed here, and the redactions are noted in the affected skills' audit verdict files.

## Tools and frameworks

No tool or framework code is vendored in this repo. The notes in tools/ and frameworks/ describe tools that run elsewhere, and each one links back to its upstream repo. The forks under the same GitHub account are the source references.

For the record, the tools and frameworks described here carry these licenses upstream: amass Apache-2.0, subfinder MIT, httpx MIT, bbot AGPL-3.0, spiderfoot MIT, theHarvester GPL-2.0, WhatWeb GPL-2.0, osmedeus MIT, OneForAll GPL-3.0, pentagi MIT, PentestGPT MIT, DeepAudit AGPL-3.0, rengine GPL-3.0, reconftw MIT, Strix Apache-2.0, Shannon AGPL-3.0.

That means no AGPL or GPL code is vendored anywhere in this repo. The GPL and AGPL tools are used as standalone tools, never folded into the MIT-licensed writing here.
