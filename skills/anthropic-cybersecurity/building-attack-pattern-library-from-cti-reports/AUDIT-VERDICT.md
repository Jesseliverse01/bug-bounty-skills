# AUDIT-VERDICT — building-attack-pattern-library-from-cti-reports

- **Source:** mukul975/Anthropic-Cybersecurity-Skills (Apache-2.0), skill `building-attack-pattern-library-from-cti-reports`
- **Domain:** cybersecurity / threat-intelligence
- **Workflow phase:** recon / enumeration / fingerprinting / vulnerability hunting / report (per-skill; see domain below)
- **Verdict: CAUTION — reference / playbook use only, authorized targets only**

## Why CAUTION (not SAFE)
- This is one of 818 skills in a bundle that includes offensive, dual-use playbooks
  (red-team C2 infrastructure, Active Directory exploitation, ransomware canaries /
  honeypots, credential dumping). Nothing here auto-executes, but the instructions
  and bundled `scripts/agent.py` / `scripts/process.py` are meant to be run against
  a target — only ever on systems Jesse owns or has explicit written authorization
  to test, per each skill's own legal notice.
- Bundled scripts are agent-invoked, not auto-run on load. Do not run them blindly;
  read the skill first and confirm the target/scope.

## Secret scan
- Bundle-wide grep (82 pattern hits, values masked) found NO live leaked secrets.
  Hits were: AWS documented example keys (`AKIA...EXAMPLE`, `...EXAMPLEKEY`),
  detection regexes, canary/honeypot bait, test fixtures (`test_with_samples`),
  and doc placeholders (`your_password`, `changeme`, localhost/example hosts).
  The `sk-` regex hits were false positives (URLs like nist.gov/ai-risk-...,
  skill-name prefixes). External hosts in scripts are legitimate APIs
  (VirusTotal, Microsoft Graph, CISA, AbuseIPDB, crt.sh, urlscan.io, GitHub);
  `evil.com` appears only as an attack-example placeholder.
- No credential literals redacted in this skill.
- 24 files bundle-wide contain `curl|bash` / `wget|bash` pipe-to-shell install
  lines for third-party tools — prefer package-manager installs; never pipe an
  unverified URL to a shell.

## Evidence
- ~/workspace/bugbounty-recon-2026-11-17/secret-hits.txt (masked secret-pattern scan, 82 hits reviewed), validate-frontmatter.py (828/828 frontmatter OK)
- Saved copies: `~/workspace/custom-skills/building-attack-pattern-library-from-cti-reports/` mirrored to `~/.agents/skills/building-attack-pattern-library-from-cti-reports/` (diff -r verified).
