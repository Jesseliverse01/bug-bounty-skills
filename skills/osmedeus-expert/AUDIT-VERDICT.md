# Osmedeus — Audit Verdict

- **Verdict: CAUTION** — reference + verified binary; install via release tarball only, never via the documented curl|bash one-liner.
- **Checked:** 2026-11-17, shallow clone `~/workspace/osmedeus-repo/` (commit at 2026-11-06 push); binary v5.1.2 verified.

## Findings

1. **curl|bash install pattern (flagged, avoided):** the README's install is `curl -sSL http://www.osmedeus.org/install.sh | bash`, and the same pattern appears in `build/DEPLOYMENT.md` and the toolbox Dockerfiles. The remote script was fetched and READ first: it is a plain prebuilt-binary downloader (npm CDN, GitHub releases fallback, installs to `~/.local/bin`, no privilege escalation, no hidden payload observed in the portion read). Even so, it was NOT executed; the binary was fetched directly from the GitHub release instead (`gh release download v5.1.2`, 50 MB tarball, verified `version` output).
2. **Secret grep:** no secrets found in the repo or in the saved skill files. No `sk-`, `AKIA`, `ghp_`, `xox`, or real key values.
3. **Auto-charge risk (flagged):** cloud runners can provision DigitalOcean/AWS/GCP/Linode/Azure infrastructure with cost controls and auto-cleanup. Enabling a cloud runner with provider credentials can spend real money — keep cloud runners off unless Jesse explicitly enables them with a budget.
4. **LLM/agentic steps:** workflow steps can call LLM providers and subprocess agents (Claude Code, Codex, OpenCode, Gemini). Those need API keys the operator supplies and can incur API charges. No key was added; no LLM step was run.
5. **No auto-execution:** the binary does nothing until a workflow/module is explicitly run (`osmedeus run -m/-f -t <target>`); `--dry-run` exists for preview. No scan was run in this check.
6. **Skill saved verbatim:** `public/skills/osmedeus-expert/SKILL.md` + `references/` copied unchanged to `~/workspace/custom-skills/osmedeus-expert/` and `~/.agents/skills/osmedeus-expert/`; `diff -r` clean on both mirrors and against source; frontmatter parses with PyYAML. No redaction was needed (no secrets in the skill).

## Why CAUTION, not SAFE

Documented install is curl|bash, cloud runners are a real spend vector, and agentic LLM steps execute subprocess agents. The project and the verified release binary are legitimate; the caution is about install method and cost-bearing optional features.

## Workflow phase

recon, enumeration, fingerprinting, vulnerability hunting, report.
