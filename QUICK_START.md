# Quick Start — LibreCopy for Grok Build

> From a clean machine to one critiqued API page in under 5 minutes.

Doctrine first: put [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine (global Grok doctrine). This pack does not replace it.

## Prerequisites

- `git`
- Grok Build installed and able to see skills under `.grok/skills/` or `~/.grok/skills/`
- A repo or product that needs shippable docs, **or** this repo as the working tree

## Layout this file assumes

Verified against this repository (do not invent extra folders):

```
skills/<name>/SKILL.md          # canonical skill bodies (copy these)
AGENTS/copy-orchestrator.md
docs/DEPTH_MATRIX.md
docs/MELT_RULES.md
.grok/skills/<name>/SKILL.md    # dogfood copy; must match skills/
.grok/plugins/librecopy-core/   # plugin stub; not required for first run
```

Melted (usable now): `skills/docs-critique/SKILL.md`, `skills/api-docs/SKILL.md`, `skills/style-guide/SKILL.md`.  
Still stubs: the other six skills + the orchestrator. Honest table: [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Install (pick one)

### A. Dogfood this repo (fastest)

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git
cd LibreCopy-Grok-Build
# Skills are already at .grok/skills/ — open this folder in Grok Build.
```

### B. Install into your docs or product repo

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git ~/LibreCopy-Grok-Build
cd /path/to/your-project
mkdir -p .grok/skills
cp -R ~/LibreCopy-Grok-Build/skills/* .grok/skills/
```

Confirm the copy landed:

```bash
test -f .grok/skills/docs-critique/SKILL.md
test -f .grok/skills/api-docs/SKILL.md
test -f .grok/skills/style-guide/SKILL.md
ls .grok/skills
```

You should see nine skill directories, matching `skills/` in this repo.

### C. User-global

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git ~/LibreCopy-Grok-Build
mkdir -p ~/.grok/skills
cp -R ~/LibreCopy-Grok-Build/skills/* ~/.grok/skills/
```

Same three `test -f` checks as B, under `~/.grok/skills/`.

Copy `AGENTS/copy-orchestrator.md` only when you want a multi-skill docs pass. It is still a stub coordinator.

## First-run teach cue

In Grok Build, on a real page you own:

1. **Write** — "Run api-docs as an API narrative. Name the integrator job. Auth, one runnable first-success call, the error they will hit. Placeholders only."
2. **Critique** — "Run docs-critique on that page: honesty, first success, examples that run, Diátaxis mix, leftover stubs."
3. **Voice (optional)** — "Run style-guide. Ten rules max. Em dashes are optional — Diego voice may use them; fail stacking, not the mark."

You used melted LibreCopy depth on Grok — not a Claude paste, not a fake plugin count.

## Hard rules

- Never embed secrets in prompts or examples.
- Honest stubs — only melted skills claim playbook depth.
- Gold Hat: empower or extract?

## Smoke checklist

- [ ] `docs-critique`, `api-docs`, and `style-guide` files exist at the install path you chose
- [ ] Grok can see those three skills
- [ ] One API page written with a named job + first-success spine
- [ ] One critique returned with severity-ranked findings and remediations (no `/10` score)
- [ ] Em dashes in examples were not treated as a hard fail
- [ ] No secrets in prompts, examples, or output

## Suite

- Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os)
- This pack: [LibreCopy-Grok-Build](https://github.com/HermeticOrmus/LibreCopy-Grok-Build)
- Sibling Libre*-Grok-Build packs: [Arch](https://github.com/HermeticOrmus/LibreArch-Grok-Build) · [DevOps](https://github.com/HermeticOrmus/LibreDevOps-Grok-Build) · [Embed](https://github.com/HermeticOrmus/LibreEmbed-Grok-Build) · [FinTech](https://github.com/HermeticOrmus/LibreFinTech-Grok-Build) · [GameDev](https://github.com/HermeticOrmus/LibreGameDev-Grok-Build) · [GEO](https://github.com/HermeticOrmus/LibreGEO-Grok-Build) · [MLOps](https://github.com/HermeticOrmus/LibreMLOps-Grok-Build) · [MobileDev](https://github.com/HermeticOrmus/LibreMobileDev-Grok-Build) · [SecOps](https://github.com/HermeticOrmus/LibreSecOps-Grok-Build) · [SessionFlow](https://github.com/HermeticOrmus/LibreSessionFlow-Grok-Build) · [UIUX](https://github.com/HermeticOrmus/LibreUIUX-Grok-Build) · [WhatsApp](https://github.com/HermeticOrmus/LibreWhatsApp-Grok-Build)
- Skills collections: [grok-skills](https://github.com/HermeticOrmus/grok-skills) · [grok-build-skills](https://github.com/HermeticOrmus/grok-build-skills)
- Claude proof (upstream, not this inventory): [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code)
- https://ormus.solutions
