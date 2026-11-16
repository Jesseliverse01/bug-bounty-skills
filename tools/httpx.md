# httpx

A fast HTTP probing toolkit, written in Go. It takes a list of hosts and probes them over HTTP: status code, title, content length, TLS certificate details, detected technologies, open ports, and paths. It sits in the pipeline between enumeration and hunting, and it is the standard way to filter a host list down to what is actually alive.

## Phase

Fingerprinting, specifically alive-host probing and technology detection. A typical chain is subfinder or amass, then httpx, then the hunting skills.

## Install

Build from source with Go, or use Docker, or take a prebuilt release binary. The build verified on this setup was v1.12.0.

```bash
go install github.com/projectdiscovery/httpx/cmd/httpx@latest
```

## Use

```bash
echo example.com | httpx
httpx -l hosts.txt -sc -title -td
httpx -l hosts.txt -json -o out.json
```

## Keys

None. No accounts, no paid features. The optional tech-detection model is a local file.

## License

MIT upstream. The tool is described here, not vendored.
