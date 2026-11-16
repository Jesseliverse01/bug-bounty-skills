# Shannon

An autonomous AI pentester for web apps and APIs, written in TypeScript. It analyzes source code, identifies attack paths, and executes real exploits to prove vulnerabilities. The rule upstream states is simple: no exploit, no report. It runs locally from a command line launcher with a worker backend, and the repo includes sample reports. The pointer skill saved from this repo lives in skills/shannon/.

## Phase

Hunting, specifically white-box web and API testing, and reporting.

## Blocker

Not installed. It needs Node and pnpm to build the monorepo, plus a model provider key of your own: Anthropic, OpenAI, xAI, AWS Bedrock, or a local model through Ollama, vLLM, or LM Studio. The launcher is interactive, and the local Ollama path was not attempted.

## Note

Anthropic and OpenAI apply cyber-safeguards to security workloads, and their legitimate-tester clearance steps have to be completed first. Keygraph never proxies model traffic.

## Keys

A provider key, unless a local model is used.

## License

AGPL-3.0 upstream. Never fold its code into an MIT-licensed repo.
