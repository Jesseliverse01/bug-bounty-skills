# reNgine

An automated reconnaissance framework with a web UI, written as a Django app. Scan engines are defined in YAML: full, passive, OSINT, and screenshot engines, with recon data correlation, continuous monitoring, per-project organisation, sub-scans on new findings, and PDF reports.

## Phase

The full pipeline: subdomain enumeration, alive-host probing, port and service scanning, fingerprinting, OSINT, vulnerability scanning, screenshots, and monitoring.

## Blocker

Not installed. Docker and Docker Compose are mandatory, and Docker is not available on this setup. The stack is PostgreSQL, Redis, the reNgine web image, nginx, and Ollama. The installer was not run.

## Safety

The compose file ships a default Postgres password. Change it before any real deployment. Optional recon API keys go in the web UI settings, added by the user.

## Keys

Optional recon API keys only. Core recon works without them, with less passive coverage.

## License

GPL-3.0 upstream. Install and use it as a tool. Never fold its code into an MIT-licensed repo.
