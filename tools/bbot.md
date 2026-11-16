# BBOT

A recursive internet scanner and attack-surface management framework, written in Python. Give it a target and it discovers subdomains, URLs, open ports, technologies, emails, and cloud buckets, chaining modules automatically and storing everything in a local event graph. The tagline upstream is the recursive internet scanner, and that is a fair description.

## Phase

Recon, enumeration, and fingerprinting in one pass. Use it as the broad sweep, then hand specific findings to focused tools. It overlaps subfinder and httpx, so pick it or them as the primary pass, not both at once.

## Install

Python 3.11 or newer. Install with pip, pipx, or Docker. The version verified on this setup was 3.1.0.

```bash
pip install bbot
```

Many modules need system tools like nmap and nuclei for full coverage. The core scanner runs without them.

## Use

```bash
bbot -t example.com -p subdomain-enum
bbot -t example.com -m httpx,sslcert
bbot -t example.com -o /path/out
```

## Keys

None needed for the baseline. Individual modules take the user's own keys in a secrets file or on the command line. Never add a key to a shared copy.

## License

AGPL-3.0 upstream. Install and use it as a tool. Never fold its code into an MIT-licensed repo, and never redistribute a modified copy without following the AGPL.
