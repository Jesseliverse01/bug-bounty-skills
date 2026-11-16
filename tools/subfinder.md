# Subfinder

A fast passive subdomain enumeration tool, written in Go. It queries certificate transparency, DNS datasets, search engines, and APIs, and returns subdomains without sending any traffic to the target itself. That makes it the quietest enumerator in this repo.

## Phase

Enumeration. It is the first tool to run after scope is set. Feed its output to httpx for alive-probing.

## Install

Build from source with Go, or use Docker, or take a prebuilt release binary. The build verified on this setup was v2.17.0.

```bash
go install github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
```

## Use

```bash
subfinder -d example.com
subfinder -dL domains.txt -o subs.txt
subfinder -d example.com -all -recursive
```

## Keys

None needed for the free sources. Extra sources like VirusTotal, Shodan, and Censys take the user's own keys in a provider config file. Never add a key to a shared copy.

## License

MIT upstream. The tool is described here, not vendored.
