---
name: scabench
description: ScaBench — a framework for evaluating AI audit agents and security tools on real-world smart-contract vulnerabilities, from Bitsec-AI (MIT). Current dataset curated-2025-08-18: 31 projects from Code4rena, Cantina and Sherlock, 555 vulnerabilities (114 high/critical), 2024-08 to 2025-08. Ships the official Nethermind AuditAgent scoring algorithm, a GPT-5 baseline runner, an HTML report generator, and a dataset generator (scrape, curate, checkout at exact commits). Use to score any vuln-finding agent before trusting it on a live hunt. Not installed, run or verified here.
---

# ScaBench: Smart Contract Audit Benchmark

A framework for evaluating security analysis tools and AI agents on real-world smart contract vulnerabilities, with curated datasets from recent audits and official tooling for consistent evaluation.

Source: https://github.com/Bitsec-AI/scabench
License: MIT (Copyright 2025 Bernhard Mueller).

## What it does

- **Curated datasets**: real-world vulnerabilities from Code4rena, Cantina and Sherlock audits.
- **Baseline runner**: LLM-based security analyzer with configurable models.
- **Scoring tool**: official Nethermind AuditAgent scoring algorithm.
- **Report generator**: HTML reports with visualizations and performance metrics.
- **Composable CLI**: end-to-end examples for a single project or all projects.

## Current dataset: curated-2025-08-18

Location: `datasets/curated-2025-08-18/curated-2025-08-18.json`

- **31 projects** from Code4rena, Cantina and Sherlock
- **555 total vulnerabilities (114 high/critical severity)**
- Time range **2024-08 to 2025-08**
- JSON with project metadata: `project_id`, `codebases` (repository URLs, commit hashes, download links), `vulnerabilities` (severity, title, detailed descriptions)

New datasets are added regularly to prevent models from being trained on known results and to maintain benchmark integrity.

## Baseline results

Location: `datasets/curated-2025-08-18/baseline-results/`

Pre-computed baselines from analyzing each individual file with GPT-5: one baseline file per project, JSON with `project`, `files_analyzed`, `total_findings`, and `findings` (title, description, severity, confidence, location, file).

## Components

- **`datasets/`** — pre-curated benchmark datasets with real vulnerabilities from audits.
- **`dataset-generator/`** — build new datasets:
  - Scrape audit platforms: `python scraper.py --platforms code4rena cantina sherlock --months 3`
  - Curate: `python curate_dataset.py --input raw_dataset.json --output curated_dataset.json --min-vulnerabilities 5 --min-high-critical 1` (drops projects with fewer than 5 vulnerabilities, no high/critical findings, inaccessible repos, or invalid/missing data)
  - Checkout sources at exact commits: `python dataset-generator/checkout_sources.py` (all projects, or a single project — see the repo README for the exact flags)
- **Scoring tool** — the official Nethermind AuditAgent scoring algorithm, applied to an agent's report against the curated ground truth.
- **Report generator** — HTML reports with visualizations and performance metrics.
- **Baseline runner** — LLM-based analyzer with configurable models.

## How this maps to Jesse's work

- This is the eval harness for any audit agent he builds: `bitsec-sandbox` is the agent template (read code, report findings with severity and confidence), `scabench` is how you score it — 31 real contest projects instead of the sandbox's 4.
- Run his own approach (or an agent built from his bug-bounty-skills repo and the cbh hunt classes) against the curated set before trusting it on a live Mantis/HackenProof hunt. A good score on known highs is the cheapest proof the method works.
- The dataset generator is the reusable part if he wants fresher ground truth: scrape recent contests, curate, checkout at exact commits.

## Limits

- Not installed, run or verified here. A full run needs a Python environment, the project checkouts, and a paid model key for the baseline runner (the pre-computed GPT-5 baselines cost money to reproduce).
- The current dataset is a snapshot (2025-08-18). Check the repo for newer datasets before benchmarking.
- Scoring uses the Nethermind AuditAgent algorithm — a benchmark score, not a bug-bounty program's severity criteria. A high benchmark score does not guarantee a submission is accepted or paid.
- The README was read via the GitHub API (truncated at 4,000 chars in that read). CLI flags beyond the ones quoted above should be taken from the repo README, not from memory.
