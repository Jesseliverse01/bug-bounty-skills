# DeepAudit

A multi-agent code audit system, written in Python with a React frontend. It runs an autonomous audit team against a codebase, verifies findings with automated sandbox proof-of-concept runs, and produces reports as PDF, Markdown, or JSON. The authors report 49 CVEs found across 17 open-source projects. It imports from GitHub, GitLab, and Gitea, and it supports a local Ollama deployment.

## Phase

Hunting, specifically source-code audit, and reporting.

## Blocker

Not installed. It needs Docker and Docker Compose, which are not available on this setup, and a model key in the backend env file. The first start also builds a sandbox image, which is heavy.

## Safety

Run it only against codebases you own or are authorized to audit. The example env file ships placeholder secrets only, which is the right way to do it.

## Keys

A model provider key, unless a local Ollama instance is used.

## License

AGPL-3.0 upstream. Never fold its code into an MIT-licensed repo.
