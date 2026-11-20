# AUDIT-VERDICT — web3-audit-corpus

- **Source:** Bitsec-AI/web3-audit-corpus (saved 2026-11-20)
- **Workflow phase:** hunting (reference library), report
- **Verdict: SAFE — reference data only, check the original before trusting a finding**

## Why SAFE
- This skill documents a public dataset of past audit reports and findings. Nothing here executes, scans, or contacts a target. It is a reference library: search past findings by class, firm, chain or project, read recorded fixes, turn them into a review checklist.
- The snapshot quoted in the skill (2026-10-22: 63 publishers, 12,767 audits, 175,640 findings) was read from the repo README via the GitHub API. Counts are as published upstream.
- The dataset itself was **not downloaded, installed or verified** here — no local copy exists. Download from the latest release and verify `CHECKSUMS.sha256` when using it.

## License note
- Derived metadata and annotations: **CC BY 4.0**, attribution "Web3 Audit Corpus, Dickson Wu, https://github.com/DicksonWu654/web3-audit-corpus". State changes when adapting the derived data and retain links to the original sources. The full data licence is kept verbatim as `LICENSE-DATA.md` in this folder.
- Quoted finding text and original reports remain the **copyright of the publishers** in `firm_id`, quoted for research, criticism and commentary. Where a publisher's notice forbids reproduction, finding bodies are withheld (`text_withheld='publisher_notice'`) and only metadata plus a source link remain. Original reports are linked, never re-hosted.
- Do not fold the corpus data into MIT-licensed writing as if it were MIT. Attribution is required.

## Notes
- AI-assisted extraction and annotation may contain errors. **Always check the linked original report** before treating a finding as fact.
- 2026 is year to date in the snapshot; the data is not live.
- Frontmatter parses clean; download table and agent-guide pointers verified present after save.
