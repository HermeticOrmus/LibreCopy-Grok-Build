# Quick Start — LibreCopy for Grok Build

> From a clean machine to one critiqued API page in under 5 minutes.

Doctrine first: put [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os) `AGENTS.md` on the machine (global Grok doctrine). This pack does not replace it.

## Prerequisites

- Grok Build (`grok --version` prints a version)
- `git` and `jq` for the clone paths and the install-everything loop
- A repo or product that needs shippable docs, **or** this repo as the working tree

## Layout this file assumes

Verified against this repository (do not invent extra folders):

```text
plugins/libre-copy-grok/                      # the Grok-native plugin
plugins/libre-copy-grok/skills/<name>/SKILL.md  # melted skill bodies (copy these for the manual path)
stubs/<name>/SKILL.md                         # stub cues; not installed
AGENTS/copy-orchestrator.md
docs/DEPTH_MATRIX.md
docs/MELT_RULES.md
.grok-plugin/marketplace.json                 # the plugin + every pack plugin, pinned
.grok/skills/<name>/SKILL.md                  # dogfood copy of the plugin skills and stubs
stubs/librecopy-core/                         # v0 plugin bundle stub, kept as the record
```

Melted (usable now): `docs-critique`, `api-docs`, `style-guide`, in `plugins/libre-copy-grok/skills/`.
Still stubs: the other six skills + the orchestrator. Honest table: [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md).

## Install (pick one)

### A. Marketplace (recommended)

```bash
grok plugin marketplace add HermeticOrmus/LibreCopy-Grok-Build
grok plugin install libre-copy-grok@libre-copy-grok --trust
grok plugin details libre-copy-grok
```

Grok installs a plugin only with `--trust`, because a plugin can run hooks, MCP servers and skills on your machine. Without it, `grok plugin install` stops and asks you to re-run with the flag.

The same marketplace lists every [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code) plugin, pinned to one commit of the pack. Install the ones your docs need by name:

```bash
grok plugin install readme-engineering@libre-copy-grok --trust
grok plugin install runbook-writing@libre-copy-grok --trust
```

Or install every entry:

```bash
for p in $(grok plugin list --json --available | jq -r '.[] | select(.marketplace == "libre-copy-grok" and .status == "available") | .name'); do
  grok plugin install "$p@libre-copy-grok" --trust
done
```

`libre-copy-hooks` is format-compatible with Grok, but its behavior inside a Grok session is not verified yet (see [LEDGER.md](./LEDGER.md)). Skip it if you only want skills and agents.

To pick up a new pin later: `grok plugin marketplace update`, then `grok plugin update`.

### B. Dogfood this repo

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git
cd LibreCopy-Grok-Build
# A copy of the skills and stubs is already at .grok/skills/. Open this folder in Grok Build.
```

### C. Copy into your docs or product repo

The v0 path, for a project that should carry the skill files itself.

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git ~/LibreCopy-Grok-Build
cd /path/to/your-project
mkdir -p .grok/skills
cp -R ~/LibreCopy-Grok-Build/plugins/libre-copy-grok/skills/* .grok/skills/
```

Confirm the copy landed:

```bash
test -f .grok/skills/docs-critique/SKILL.md
test -f .grok/skills/api-docs/SKILL.md
test -f .grok/skills/style-guide/SKILL.md
ls .grok/skills
```

You should see three skill directories, matching `plugins/libre-copy-grok/skills/` in this repo. The stubs are not copied: they are pointers to pack plugins, not skills.

### D. User-global copy

```bash
git clone https://github.com/HermeticOrmus/LibreCopy-Grok-Build.git ~/LibreCopy-Grok-Build
mkdir -p ~/.grok/skills
cp -R ~/LibreCopy-Grok-Build/plugins/libre-copy-grok/skills/* ~/.grok/skills/
```

Same three `test -f` checks as C, under `~/.grok/skills/`.

### Upgrading from v0

If you copied `skills/*` into a project or `~/.grok/skills/`, that copy holds all nine folders, stubs included. Remove the six stub folders (`readme-engineering`, `runbook-writing`, `changelog-discipline`, `error-messages`, `tutorial-creation`, `anti-slop`) from the copy, or replace the copy with path A so updates arrive through `grok plugin update`.

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

- [ ] `grok plugin list` shows `libre-copy-grok` (path A), or the three skill files exist at the copy path you chose (C or D)
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
