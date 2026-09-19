# Quick Start — LibreCopy for Grok Build

> From zero to a docs review cue in under 5 minutes.

## Prerequisites

- Grok Build installed and working
- A repo or product that needs shippable docs

## Install skills (repo-local)

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git
cd your-project
mkdir -p .grok/skills
cp -R /path/to/LibreCopy-Grok-Build/skills/* .grok/skills/
```

Or user-global:

```bash
mkdir -p ~/.grok/skills
cp -R /path/to/LibreCopy-Grok-Build/skills/* ~/.grok/skills/
```

## First-run teach cue

1. **README** — "Run readme-engineering on the landing page."
2. **Anti-slop** — "Run anti-slop to strip AI tells."
3. **Runbook** — "Run runbook-writing for one operational procedure."

## Hard rules

- Never embed secrets in prompts or examples.
- Honest stubs — melt depth next.
- Gold Hat: empower or extract?

## Smoke checklist

- [ ] Skills visible to Grok
- [ ] One skill run produces measurable output
- [ ] No secrets in output
