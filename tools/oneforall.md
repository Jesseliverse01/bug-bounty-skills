# OneForAll

A subdomain collection tool, written in Python. It combines certificate transparency, DNS dataset, and search-engine collection with DNS brute-forcing from built-in wordlists and a subdomain takeover check. It is one of the most complete single-purpose subdomain enumerators, but it is also the oldest codebase in this repo: the docs and dependency pins are from 2022, and the last upstream push was in November 2026 after a long quiet stretch.

## Phase

Enumeration. It is an alternative to subfinder and amass when a brute-force wordlist pass and a built-in takeover check are wanted in one run. It overlaps subfinder heavily, so pick one as the primary enumerator, not both.

## Install

Python 3.6 or newer, with the pinned requirements. Docker is also an option. The version verified on this setup was 0.4.5.

```bash
pip install -r requirements.txt
python oneforall.py --help
```

## Keys

None needed for the baseline. Optional API keys for the many passive sources go in the config file, supplied by the user. Never add a key to a shared copy.

## License

GPL-3.0 upstream. Install and use it as a tool. Never fold its code into an MIT-licensed repo.
