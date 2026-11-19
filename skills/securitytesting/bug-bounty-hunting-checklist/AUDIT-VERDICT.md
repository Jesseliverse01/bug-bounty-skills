# AUDIT-VERDICT — bug-bounty-hunting-checklist

- **Source:** The-XSS-Rat/SecurityTesting, `Checklists/HuntingCheckList.md` (saved 2026-11-20)
- **Workflow phase:** hunting (web application), report
- **Verdict: CAUTION — authorized targets only, in-scope testing**

## Why CAUTION
- This is a methodical hunting checklist: strategy, recon, session/cookie/auth
  checks, SQLi, XSS (stored/reflected/DOM/blind/evasion), SSTI, command
  injection, CSRF, IDOR, LFI/RFI, file upload, XXE, SSRF, open redirect,
  security headers, and chaining. The payloads are textbook examples, not a
  runner — nothing here executes anything by itself.
- Every section assumes an in-scope, authorized target. The checklist itself
  says it: PoC or GTFO, prove impact, report through the program. Testing
  outside a published scope is out of bounds.
- No tool was installed and no scan was run from this checklist; it was saved
  as reference only.

## License note
- The upstream repo has **no LICENSE file and states no license**, so this
  skill is reproduced here with attribution and is **not relicensed**. Do not
  fold it into MIT-licensed writing as if it were MIT.

## Notes
- No secrets found in the checklist (grep for key/token patterns clean).
  The only URLs are public learning videos and tools (Burp Collaborator,
  interactsh, XSS Hunter, tplmap, sqlmap).
- Blind XSS section references xsshunter.com (third-party service; needs its
  own account, nothing wired here).
- Frontmatter parses clean; 18 sections verified present after save.
