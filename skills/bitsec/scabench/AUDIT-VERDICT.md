# AUDIT-VERDICT — scabench

- **Source:** Bitsec-AI/scabench (saved 2026-11-20)
- **Workflow phase:** hunting (evaluation harness), report
- **Verdict: SAFE — benchmark tooling, needs a paid model key to run**

## Why SAFE
- This skill documents a benchmark framework for evaluating AI audit agents on real-world vulnerabilities from Code4rena, Cantina and Sherlock contests. Nothing here executes against a live target. It scores an agent's report against curated ground truth.
- The dataset quoted in the skill (curated-2025-08-18: 31 projects, 555 vulnerabilities, 114 high/critical, 2024-08 to 2025-08) was read from the repo README via the GitHub API. The README read was truncated at 4,000 chars, so CLI flags beyond the ones quoted in the skill should be taken from the repo README, not from memory.
- The framework was **not installed, run or verified** here. A full run needs a Python environment, the project checkouts, and a paid model key for the baseline runner (the pre-computed GPT-5 baselines cost money to reproduce).

## License note
- **MIT**, Copyright 2025 Bernhard Mueller. The full license text is kept verbatim as `LICENSE` in this folder.

## Notes
- The current dataset is a snapshot (2025-08-18). Check the repo for newer datasets before benchmarking — new sets are added regularly so models cannot train on known results.
- Scoring uses the Nethermind AuditAgent algorithm — a benchmark score, not a bug-bounty program's severity criteria. A high benchmark score does not guarantee a submission is accepted or paid.
- No secrets found in the README content reviewed (no keys, tokens or credentials).
- Frontmatter parses clean; dataset counts and component list verified present after save.
