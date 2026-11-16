# Strix

An autonomous AI pentesting CLI, written in Python. Multi-agent teams recon, exploit, and validate findings with working proof-of-concepts, then auto-fix and report in Markdown, JSON, CSV, or SARIF. A managed cloud option exists upstream. The 9 skills saved from this repo live in skills/strix/.

## Phase

Hunting, for web apps, APIs, and code, plus CI scanning, remediation, and reporting.

## Blocker

Not installed. It needs Docker running, which is not available on this setup, and a model API key through LiteLLM. The first run also pulls a sandbox Docker image. The dependency set is heavy, so installing the CLI alone was not attempted.

## Install, when the blockers are gone

```bash
pipx install strix-agent
```

Prefer pipx over the curl-to-bash installer upstream documents.

## Keys

A model provider key: OpenAI, Anthropic, Google, or others through LiteLLM. The managed cloud path needs a Strix account and bought credits.

## License

Apache-2.0 upstream.
