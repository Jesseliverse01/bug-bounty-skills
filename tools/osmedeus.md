# Osmedeus

An orchestration engine for security work, written in Go. Workflows are defined in YAML, in two kinds: modules, which are single execution units, and flows, which orchestrate modules with dependencies, hooks, decision routing, and conditional branching. It can run on a host, in Docker, or over SSH, with distributed execution through Redis, cron and file-watch triggers, a REST API, and a web UI. It also has agentic steps that call a language model.

## Phase

The full pipeline as an orchestrator. It runs other tools, subdomain enumeration, probing, and scanning, through workflows, and it covers reporting too. Use it when you would rather orchestrate than type each command yourself.

## Install

The documented install is a curl-to-bash one-liner, which is not the way to install it. The script was read first: it only downloads a prebuilt binary, but piping an installer to a shell is still a bad habit. Get the release binary instead. The version verified on this setup was 5.1.2.

```bash
gh release download v5.1.2 --repo j3ssie/osmedeus --pattern 'osmedeus_5.1.2_linux_amd64.tar.gz'
./osmedeus version
```

Building from source needs Go 1.26.

## Keys

None for the core engine. Optional: model provider keys for the agentic steps, cloud keys for cloud runners, and service keys inside individual workflows. Cloud runners can incur charges, so check the cost controls before enabling them.

## License

MIT upstream. The skill for driving it lives in skills/osmedeus-expert/. The tool itself is described here, not vendored.
