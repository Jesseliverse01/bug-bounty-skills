# SpiderFoot

OSINT automation with over 200 modules, written in Python. It takes a domain, IP, email, or username and gathers what is publicly known about it, with a web UI or a command line interface, a SQLite backend, and a correlation engine that links findings together. It has been developed since 2012 and is stable rather than fast-moving.

## Phase

Recon and OSINT. Passive by default, with some modules doing active DNS queries or calling other tools. It covers the people and infrastructure around a target, which the enumerators do not.

## Install

Python 3.7 or newer, with the pinned dependencies in requirements.txt. Docker is also an option. The version verified on this setup was 4.0.0.

```bash
pip install -r requirements.txt
python sf.py --help
```

## Keys

Many modules accept optional API keys, Shodan, VirusTotal, SecurityTrails, and others. All are optional. SpiderFoot works without them, with less coverage. Keys go in the web UI config, added by the user.

## License

MIT upstream. The tool is described here, not vendored. A paid cloud tier exists upstream and was not used.
