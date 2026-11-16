# AUDIT-VERDICT — strix-api-security-testing

- **Source:** usestrix/strix (Apache-2.0), skill `api-security-testing`
- **Workflow phase:** vulnerability hunting (API: OWASP API Top 10)
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
- Saved copies: `~/workspace/custom-skills/strix-api-security-testing/` mirrored to `~/.agents/skills/strix-api-security-testing/` (diff -r verified).
- **Folder renamed:** upstream skill name `api-security-testing` collided with a pre-existing unrelated skill of the same name in `~/workspace/custom-skills/` (dated 2026-02-27, personal workflow, 3.6 KB). Saved as `strix-api-security-testing` in both locations; SKILL.md content (including frontmatter `name:`) is verbatim upstream.

