# AUDIT-VERDICT — fix-security-vulnerabilities-with-strix

- **Source:** usestrix/strix (Apache-2.0), skill `fix-security-vulnerabilities-with-strix`
- **Workflow phase:** report / remediation (patch + re-scan)
- **Verdict: CAUTION — live exploitation; authorized targets only**

## Why CAUTION
- These skills drive Strix autonomous agents that actively exploit a target and
  produce working PoCs. Only run against apps/APIs/code Jesse owns or is
  explicitly authorized to test.
- Running Strix needs Docker (not available on this VM) plus an LLM API key
  (OpenAI/Anthropic/Google/etc. via `LLM_API_KEY`) — no key was wired, no CLI
  installed, no scan run. The managed-cloud skill needs a Strix account/credits.

## Secret scan
- No hardcoded secrets found in the 9 Strix SKILL.md files (grep for sk-/AKIA/ghp_/xox/private-key/api_key=/password= clean).
- Frontmatter parses clean with PyYAML (9/9).

## Evidence
- ~/workspace/bugbounty-recon-2026-11-17/secret-hits.txt (masked secret-pattern scan, 82 hits reviewed), validate-frontmatter.py (828/828 frontmatter OK)
- Saved copies: `~/workspace/custom-skills/fix-security-vulnerabilities-with-strix/` mirrored to `~/.agents/skills/fix-security-vulnerabilities-with-strix/` (diff -r verified).
