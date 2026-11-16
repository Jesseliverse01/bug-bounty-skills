# theHarvester

An OSINT harvester, written in Python. It gathers emails, subdomains, hosts, and employee names for a domain or a company from search engines, certificate transparency, DNS, and APIs. It also ships a small web UI and a report generator.

## Phase

Recon and enumeration, on the OSINT side. It answers who and what is attached to a target before any probing starts.

## Install

Python 3.14 or newer. That matters, because most systems still ship an older Python. The install verified on this setup used uv to fetch CPython 3.14.10, then installed theHarvester into a virtual environment. The version verified was 5.0.0.

```bash
uv python install 3.14
uv pip install theHarvester
```

## Use

```bash
theHarvester -d example.com -b bing
theHarvester -d example.com -b all -f out.html
```

## Keys

The api-keys.yaml file ships with all key fields empty, and that is how it should stay in a shared copy. Per-source keys are optional and documented in the repo wiki. Keyless sources work without them.

## License

GPL-2.0 upstream. Install and use it as a tool. Never fold its code into an MIT-licensed repo.
