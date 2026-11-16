# Amass

OWASP's attack surface mapping and asset discovery tool, written in Go. It enumerates subdomains from passive sources, certificate transparency, DNS datasets, and DNS brute-forcing, then maps the external attack surface: IPs, ASNs, netblocks, and the relationships between assets, with a local graph database and visualisation output.

## Phase

Enumeration and attack-surface mapping. It sits at the start of the pipeline, right after scope is set. A typical chain is amass for enumeration, then httpx to see which hosts are alive.

## Install

Build from source with Go 1.27 or newer, or use Docker, or take a prebuilt release binary from the upstream releases page. The build verified on this setup was v5.1.3.

```bash
go install github.com/owasp-amass/amass/v5/cmd/amass@latest
```

## Use

```bash
amass enum -d example.com
amass enum -d example.com -brute
amass intel -whois -d example.com
```

Only run it against a target inside a published scope. The brute-force mode is noisy, so it belongs later in a hunt, not in the first pass.

## Keys

None needed for the baseline. Optional data sources like Shodan, Censys, and VirusTotal take the user's own keys in a config file. Never add a key to a shared copy.

## License

Apache-2.0 upstream. The tool is described here, not vendored.
