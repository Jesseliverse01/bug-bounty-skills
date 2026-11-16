# Pipeline

How the contents of this repo fit together, in the order you actually use them.

## Read the scope first

Before any tool runs, read the program scope and write down what is in scope, what is out of scope, and what the program pays for. Everything after this step answers to that list. If the scope does not cover a host, you do not touch it. This is the one rule with no exceptions.

## Quiet recon

Start with sources that send no traffic to the target. Subfinder queries passive sources for subdomains. Amass does the same and adds certificate transparency, DNS datasets, and attack-surface mapping with IPs and netblocks. TheHarvester gathers emails, subdomains, hosts, and employee names from search engines and APIs. Spiderfoot automates the OSINT side with over 200 modules, from domains and IPs to usernames and emails.

The output of this phase is a list of hosts and some context about the organization. Nothing here proves a vulnerability. It only tells you where to look next.

## Fingerprinting

Take the host list and probe it. Httpx answers which hosts are alive and what they return: status, title, TLS details, and detected technologies. WhatWeb identifies what each site runs, CMS, frameworks, server headers, and libraries, using over a thousand plugins.

Knowing the stack picks the right checks. A WordPress host and a custom API get different playbooks, and guessing wastes time. OneForAll can run as a second opinion on subdomains here, since it adds DNS brute-forcing and a takeover check in one pass.

BBOT covers the same ground in one recursive run when you want breadth over precision: subdomains, URLs, ports, technologies, emails, and cloud buckets, chained automatically. Osmedeus does the same as an orchestrator, running other tools through YAML workflows.

## Hunting

This is where the skills do the work. The Claude-BugHunter set carries the vulnerability classes, 82 skills built from disclosed reports, with triage discipline for deciding what is worth chasing. The Agentic-Bug-Hunter set carries the workflow from recon to report, 25 skills that tie the phases together. The Anthropic shelf covers 29 domains in depth, so a hunt that lands on a specific technology has a playbook ready. The Strix skills cover web, API, code, and OWASP testing.

Pick the skill that matches the target and the vulnerability class, read it first, and follow its steps. Do not run a skill you have not read. Check the audit verdict in the skill folder; some skills are reference only.

## Validating

A scanner alert is not a finding. Reproduce the bug with the smallest proof that shows it, and write the exact steps down. Check the impact honestly: who is affected, what an attacker can actually do, and what it would take to fix. If you cannot reproduce it, log it as unconfirmed and move on.

Two habits keep reports honest. First, write the kill condition before you invest hours: what would make you drop this lead. Second, keep the null results. A hunt that finds nothing is still a result, and writing it down keeps you from repeating the same dead end next week.

## Reporting

Write the report for the person who has to fix the bug. Title, what it is, where it is, how to reproduce it, what the impact is, and what a fix looks like. Keep it short and keep every claim tied to something you actually observed.

Nothing in this repo files the report for you. Reports go through your own account on the bounty platform, in the format that program asks for. Check the program rules for proof requirements before you submit, since some programs ask for a reproducing test and some ask for a video or a specific template.

## What stays reference

The frameworks in frameworks/ are documented, not installed. Most need Docker or a model key, and this setup has neither. The three full-pipeline orchestrators, rengine, reconftw, and osmedeus, overlap heavily. Pick one when the time comes to deploy one properly, instead of running all three.
