# reconFTW

A Bash framework that orchestrates over 70 external tools. One command runs subdomain enumeration, web probing, OSINT, and vulnerability scanning, with resumable checkpoints, structured output per domain, monitor mode, optional distributed execution, AI reporting with a local model, and notifications to Slack, Telegram, or Discord.

## Phase

The full pipeline: enumeration, probing, OSINT, fingerprinting, hunting, and reporting.

## Blocker

Not installed. The installer was not run, because it installs system-wide: a large apt package list, around 55 Go tools, plus git clones and pip installs. The framework script itself runs under Bash, and its help output was verified, but a full run needs the toolchain and the tools it orchestrates.

## Keys

All optional, in a gitignored secrets file or environment variables: Shodan, WhoisXML, ProjectDiscovery Cloud, GitHub tokens, and webhook URLs. No key was added.

## License

MIT upstream.
