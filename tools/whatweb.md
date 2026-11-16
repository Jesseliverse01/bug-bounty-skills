# WhatWeb

A web fingerprinter, written in Ruby. It identifies what a website runs, CMS, JavaScript libraries, frameworks, server headers, cookies, IP, and country, using over a thousand plugins. Aggressive mode can also guess versions, emails, and account IDs.

## Phase

Fingerprinting. It is the narrowest tool in this repo: one job, identify the stack, done well. Knowing the stack picks the right checks, so it feeds directly into hunting.

## Install

Ruby 3.x plus a few gems. The version verified on this setup was 0.6.4.

```bash
apt-get install -y ruby
gem install addressable
ruby whatweb --version
```

## Use

```bash
whatweb example.com
whatweb -a 3 example.com
whatweb --log-json out.json example.com
```

## Keys

None. Fully offline-capable fingerprinting, no accounts, no paid APIs.

## License

GPL-2.0 upstream. Install and use it as a tool. Never fold its code into an MIT-licensed repo.
