# LibreCopy-Grok-Build

**Technical writing / docs-as-code skills for Grok Build** — ported and melted from [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code), not a dumb copy.

> Status: **v0 public scaffold** — honest stubs. Melt depth next.

## Why this exists

AI docs have tells. LibreCopy owns README engineering, API docs, runbooks, changelogs, anti-slop — melted for Grok Build from LibreCopy-Claude-Code. Feeds every suite README.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md).

```bash
mkdir -p .grok/skills
cp -R skills/* .grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth matrix (honest)

| Artifact | v0 scaffold | Upstream Claude (proof) |
|----------|-------------|-------------------------|
| Skills (melted bodies) | 8 stubs → fill next | see upstream suite |
| Agents | 1 (`copy-orchestrator`) | upstream agents |

Counts on the right are **upstream proof**, not this repo's claim until melted.

## First skills

| Skill | Job |
|-------|-----|
| readme-engineering | README structure that gets someone productive fast (Diátaxis-aware) |
| api-docs | API reference + examples + error codes that stay true |
| runbook-writing | Incident / ops runbooks: trigger, steps, rollback, owners |
| changelog-discipline | What belongs in CHANGELOG — semver honesty |
| error-messages | Actionable error UX — no blame, clear next step |
| tutorial-creation | Tutorial sequencing that teaches while helping |
| style-guide | Voice, vocabulary, and formatting rules for the suite |
| anti-slop | Strip AI-doc tells: adjective stacks, soft closes, empty catalogs |

Agent: `AGENTS/copy-orchestrator.md` — full suite pass.

## Layout (Grok Build)

```
skills/                 # install into .grok/skills or ~/.grok/skills
AGENTS/                 # suite agents
.grok/plugins/          # optional plugin bundle
docs/                   # DEPTH_MATRIX, MELT_RULES
```

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract?

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- Sibling: [LibreUIUX-Grok-Build](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [LibreSessionFlow-Grok-Build](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [LibreGEO-Grok-Build](https://github.com/HermeticOrmus/LibreGEO-Grok-Build)
- Skills packs: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof: [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
