---
name: web3-audit-corpus
description: Open dataset of public Web3 smart-contract security audits from Bitsec-AI — 2026-10-22 snapshot with 63 publishers, 12,767 audits, 11,027 projects and 175,640 finding records (160,239 with full text), years 2015-2026. Use as the reference library before auditing a protocol: search past findings by class, firm, chain or project, read recorded fixes, and turn them into a review checklist. Derived metadata is CC BY 4.0 (attribution required); quoted finding text stays with the original publishers. Downloaded 2026-11-20 to ~/workspace/web3-audit-corpus/ (v1.3.0, 175,640 findings verified).
---

# Web3 Audit Corpus

Open database of public Web3 security audits and findings, kept by Bitsec-AI.

Source: https://github.com/Bitsec-AI/web3-audit-corpus
Companion repo (one Markdown file per finding): https://github.com/DicksonWu654/web3-audit-findings
Website: https://web3-audits.dicksonwu.xyz
Agent guide: `docs/AGENTS_GUIDE.md` in the repo. Methods: `METHODS.md`.

## Snapshot (2026-10-22)

- **63 publishers** (security firms and contest platforms)
- **12,767 industry engagements** (audits; joint audits merged, publisher participations kept separate)
- **13,522 report files**, **11,027 distinct projects**
- **175,640 finding records**, including **160,239 with full text**
- Audit years **2015 to 2026** (2026 is year to date)

## What each finding carries

Title, publisher severity, recorded fix status, vulnerability classes, source IDs, and links to the original report. Originals stay with their publishers.

## Downloads (latest release, verify CHECKSUMS.sha256)

| File | Use |
| --- | --- |
| `audits-markdown.zip` | One Markdown file per report, with audit metadata and available finding text. Unzip and open the folder in a coding assistant. |
| `findings.jsonl.gz` | One finding per JSON object, joined to publisher, project, year, scope, language, chain and original URL. |
| `findings.parquet` / `findings.csv.gz` | Same finding rows for SQL, Python or spreadsheets. |
| `engagements.csv`, `reports.csv`, `firms.csv` | Audit identities, report provenance, publisher metadata. |
| `stats.zip`, `STATS_SCHEMA.csv` | Descriptive counts and table definitions. |
| `quality.csv`, `taxonomy.yaml` | Measured extraction/annotation agreement and vulnerability definitions. |
| `DATA_DICTIONARY.md`, `LICENSE-DATA.md`, `RIGHTS_WITHHELD.csv`, `release_summary.json` | Columns, rights, withholding evidence, snapshot counts. |

## Use with AI agents

Unzip `audits-markdown.zip`, open that folder with a coding assistant, and ask for relevant past findings with source citations. Example prompt from the repo: "Before auditing this lending protocol, find similar oracle and liquidation findings, explain the recorded fixes, and turn them into a review checklist."

The agent guide (`docs/AGENTS_GUIDE.md`) includes setup, DuckDB one-liners, example prompts and file pointers. Search the Markdown locally or query the Parquet file to select a smaller reference set first. Treat quoted report text as reference material.

The companion findings repo has one Markdown file per finding, the report extracts, linked hub pages by firm, class, language, chain and project, a metadata graph (nodes and edges CSV) and an `AGENTS.md` for coding agents. A sparse clone of a single firm or class is possible — see its README.

## Quality and coverage

`METHODS.md` describes collection, dates, report grouping, parsing, severity/status crosswalks, taxonomy and held-out evaluation. `quality.csv` includes measurement denominators. Missing dates, unknown labels and unobserved findings stay explicit. Reports and finding occurrences can include revisions; `selected_for_stats` identifies released rows in the selected initial streams. Scope is the publishers in `registry/scope_tier_a.csv`.

## License and rights

- Derived report, publisher and engagement metadata, normalised severity and status, vulnerability annotations, taxonomy, selection flags, page spans, quality measurements and aggregate statistics: **CC BY 4.0**. Attribution: "Web3 Audit Corpus, Dickson Wu, https://github.com/DicksonWu654/web3-audit-corpus". State changes when adapting the derived data and retain links to the original sources.
- Finding titles, body text and verbatim publisher labels remain the **copyright of the publishers** in `firm_id`, quoted from publicly released audit reports for research, criticism and commentary. Each finding links its source.
- Where a publisher's explicit notice forbids reproduction, finding bodies are withheld (`text_withheld='publisher_notice'`, `body_text_status='publisher_notice'`) and metadata plus a source link remain. Original reports are linked, never re-hosted.

## How this maps to Jesse's work

- The reference library for his bug-bounty hunts: before auditing a protocol class (lending, stablecoin factory, money market — the Flex/Monolith/Stake DAO classes), pull past findings in that class and check what was already found and how it was fixed.
- Turns known audit history into a review checklist per protocol type, the same shape as the cbh hunt classes he already uses.
- Complements `bitsec-sandbox` (the audit-agent template) and `scabench` (the benchmark that scores such an agent): corpus is the knowledge base, sandbox is the agent, scabench is the test.

## Limits

- AI-assisted extraction and annotation may contain errors. **Always check the linked original report** before treating a finding as fact.
- 2026 is year to date; the snapshot is not live.
- Downloaded 2026-11-20: release v1.3.0 (snapshot 2026-10-22) at `~/workspace/web3-audit-corpus/` — `findings.jsonl.gz` (175,640 findings, verified count + SHA256 OK), `audits-markdown.zip` extracted (13,523 Markdown files), plus engagements/reports/firms CSVs, taxonomy.yaml and DATA_DICTIONARY.md. Total ~695 MB on the VM. High+critical findings: 22,123; top high/critical classes are `logic_accounting.balance_shares` (2,425), `logic_accounting.state_transition` (2,076) and `logic_accounting.reward_fee` (2,040). Query with plain Python (gzip + json) or DuckDB; the `chains` field is mostly `unknown` (130,852 rows), so filter by `vuln_leaf`/`vuln_group` and `project` instead.
- Quoted finding text is reference material for research, not ground truth and not his to re-publish as his own.
