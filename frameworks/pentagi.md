# PentAGI

A self-hosted multi-agent system for fully autonomous penetration testing, written in Go. You give it a target and a goal in plain language, and a team of specialist agents plans and runs over 20 professional tools, nmap, Metasploit, sqlmap, and others, inside an isolated Docker sandbox. Results go to PostgreSQL, with an optional knowledge graph, and the system exposes a REST and GraphQL API plus a web UI.

## Phase

The whole pipeline, end to end: recon, enumeration, hunting, and reporting, run autonomously.

## Blocker

Not installed. It needs Docker and Docker Compose, which are not available on this setup, and a language model provider key. A local model through Ollama or vLLM is an option instead of a paid key.

## Safety

The compose file ships default Postgres credentials, postgres as both user and password, overridable with an environment variable. Change them before any real deployment. Autonomous live exploitation belongs only on targets with written authorization.

## Keys

A model provider key, unless a local model is used.

## License

MIT upstream. No skill content ships in the repo, so nothing from it was saved as a skill.
