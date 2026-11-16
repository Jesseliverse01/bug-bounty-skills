# AUDIT-VERDICT — shannon

- **Source:** KeygraphHQ/shannon (AGPL-3.0), plugin skill `plugins/shannon/skills/shannon/SKILL.md`
- **Workflow phase:** vulnerability hunting (white-box web/API exploit validation), report
- **Verdict: CAUTION — live exploitation; authorized targets only**

## Why CAUTION
- Shannon actively exploits the target and can create, change, and delete data.
  The skill itself enforces good gates (confirm ownership + authorization, never
  production, never run `reset`, never paste a provider key into chat) — follow them.
- Needs a BYO LLM provider key (Anthropic/OpenAI/xAI/AWS Bedrock, or local Ollama)
  — no key was wired, nothing installed, no scan run. Anthropic/OpenAI apply
  cyber-safeguards to security workloads; their tester-clearance steps apply.
- AGPL-3.0: never fold Shannon code into Jesse's MIT repos.

## Notes
- The upstream SKILL.md is a thin pointer: it references `llms.txt` /
  `llms-full.txt` at the plugin root (`../../llms.txt`). Those two docs were
  copied into this skill folder for self-containment; SKILL.md itself is verbatim.
- No hardcoded secrets found in the skill or the two llms docs (placeholders only,
  e.g. `export ANTHROPIC_API_KEY=your-...`).
- Frontmatter parses clean with PyYAML.

## Evidence
- ~/workspace/bugbounty-recon-2026-11-17/secret-hits.txt (masked secret-pattern scan, 82 hits reviewed), validate-frontmatter.py (828/828 frontmatter OK)
- Saved copies: `~/workspace/custom-skills/shannon/` mirrored to `~/.agents/skills/shannon/` (diff -r verified).
