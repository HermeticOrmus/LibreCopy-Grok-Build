# LibreCopy-Grok-Build

**Technical writing / docs-as-code skills for [Grok Build](https://github.com/HermeticOrmus/grok-build-reality-os)** — ported and melted from [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code), not a dumb copy.

> Status: **public v0** — three skills melted (`docs-critique`, `api-docs`, `style-guide`); the rest are honest stubs. See [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Why this exists

AI docs have tells. LibreCopy owns README engineering, API narrative, runbooks, changelogs, anti-slop. Grok Build needs the same *job* with Grok-native skills, `.grok/`, and truth-seeking voice. This repo counts only what it has melted.

## Install (<5 min)

See [QUICK_START.md](./QUICK_START.md) for clone, dogfood, project-local, and user-global paths.

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git
cd LibreCopy-Grok-Build
# Dogfood: .grok/skills/ already has the skill bodies.
# Other project: cp -R skills/* /path/to/your-project/.grok/skills/
```

Doctrine: install [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine first.

## Depth / quality

This pack targets **L3–L4 hygiene** on the Reality OS [quality ladder](https://github.com/HermeticOrmus/grok-build-reality-os/blob/main/docs/QUALITY_LADDER.md) (SECURITY linked, contributing describes this repo, inventory honest, suite map complete). Melted skills are inventory in [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md). This pass does not claim L5.

| Artifact | This repo now | Upstream Claude |
|----------|---------------|-----------------|
| Skills | 3 melted + 6 stubs | Proof the job exists; not our inventory |
| Agents | 1 stub (`copy-orchestrator`) | Proof the job exists; not our inventory |
| Plugins | 1 core bundle stub | Proof the job exists; not our inventory |

Do not paste Claude plugin/agent/command totals here. Update [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md) when something melts.

## Skills

| Skill | Status | Job |
|-------|--------|-----|
| docs-critique | melted | Daily critique loop for one page |
| api-docs | melted | API narrative: auth, first success, the error they will hit |
| style-guide | melted | Ten-rule voice. Em dashes optional (Diego voice) |
| readme-engineering | stub | README structure (Diátaxis-aware) |
| runbook-writing | stub | Incident / ops runbooks |
| changelog-discipline | stub | CHANGELOG + semver honesty |
| error-messages | stub | Actionable error UX |
| tutorial-creation | stub | Tutorial sequencing |
| anti-slop | stub | AI-doc tells |

Agent: `AGENTS/copy-orchestrator.md` — stub coordinator for a full docs pass.

## Layout (Grok Build)

```
skills/                 # canonical SKILL.md bodies
AGENTS/                 # suite agents
docs/                   # DEPTH_MATRIX, MELT_RULES
.grok/skills/           # dogfood copy of skills/ (keep in sync)
.grok/plugins/          # optional plugin bundle stub
```

Claude's `.claude/` maps to Grok skills + `AGENTS.md` + `.grok/`. Melt rules: [docs/MELT_RULES.md](./docs/MELT_RULES.md).

## Gold Hat

[GOLD_HAT.md](./GOLD_HAT.md) — empower or extract? Canonical manifesto: [gold-hat-manifesto](https://github.com/HermeticOrmus/gold-hat-manifesto).

Teach the writing move. Do not leave the reader dependent on the skill.

## Security

[SECURITY.md](./SECURITY.md) — this pack is docs and prompts. Still: never embed secrets in skills, templates, or examples.

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreCopy-Grok-Build](https://github.com/HermeticOrmus/LibreCopy-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [GEO](https://github.com/HermeticOrmus/LibreGEO-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [UIUX](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof (upstream, not this inventory): [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code)
- https://ormus.solutions

## License

MIT — see [LICENSE](./LICENSE).
