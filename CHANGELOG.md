# Changelog

## [1.0.0] - 2026-09-30

The Grok edition: the melted skills install as a Grok plugin, and the same marketplace installs every LibreCopy-Claude-Code plugin, pinned to one commit of the pack. The [kintsugi ledger](./LEDGER.md) records each v0 crack and its seal.

### Added

- `plugins/libre-copy-grok/`, the Grok-native plugin (`.grok-plugin/plugin.json`, version 1.0.0) with the three melted skills: `docs-critique`, `api-docs`, `style-guide`.
- `.grok-plugin/marketplace.json` (`libre-copy-grok`): the Grok-native plugin plus all 21 LibreCopy-Claude-Code plugins as remote entries pinned to pack commit `8ec68f353913bfd5cb087c621247a71f6448efe7`.
- `scripts/pin-pack.sh`: re-pins the pack entries to the pack's `main`, adds new pack plugins, drops removed ones, and prints the diff; `--check` fails on an unreachable SHA or a changed plugin list.
- `.github/workflows/validate.yml`: `grok plugin validate`, the dogfood copy check, the doc install-line check, the pin check, and an install of every entry into a clean `GROK_HOME`.
- Issue forms for feedback, routing misses and plugin proposals, with the `feedback`, `routing-miss` and `plugin-proposal` labels.
- [LEDGER.md](./LEDGER.md), [stubs/README.md](./stubs/README.md), and "Ways to contribute" in [CONTRIBUTING.md](./CONTRIBUTING.md).

### Changed

- Install is `grok plugin marketplace add HermeticOrmus/LibreCopy-Grok-Build` then `grok plugin install libre-copy-grok@libre-copy-grok --trust`. The folder copy still works from the new path, `plugins/libre-copy-grok/skills/*`.
- Melted skills moved from `skills/` to `plugins/libre-copy-grok/skills/`; the six stubs moved to `stubs/`. The `.grok/skills/` dogfood copy stays and matches both.
- The v0 bundle stub `.grok/plugins/librecopy-core/` moved to `stubs/librecopy-core/`, marked superseded.
- README gains the family header, the marketplace install and the real Depth table; QUICK_START, AGENTS.md, DEPTH_MATRIX and MELT_RULES follow the new paths.

### Fixed

- Stubs no longer install as if they were playbooks: their descriptions start "Stub, not a playbook." and name the pack plugin that holds the real depth. `anti-slop` says honestly that no pack plugin covers it one to one and names the nearest.
- The v0 plugin folder installed as an unversioned plugin with no skills; the new plugin validates with its three skills.

### Upgrading from v0

- If you copied `skills/*` into a project or `~/.grok/skills/`, remove the six stub folders from that copy, or switch to the marketplace install so `grok plugin update` brings changes.
- Paths that pointed at `skills/<name>` now point at `plugins/libre-copy-grok/skills/<name>` (melted) or `stubs/<name>` (stubs).
- `grok plugin install` needs `--trust`; without it Grok stops and asks for a re-run with the flag.

## [0.1.0] — 2026-09-20

### Added

- Melted `skills/docs-critique/SKILL.md` (new): daily page critique — honesty, first success, runnable examples, severity, leftovers.

### Changed

- Melted `skills/api-docs/SKILL.md` into an API narrative skill (job, auth, first success, error they will hit, Diátaxis, change-policy handoff).
- Melted `skills/style-guide/SKILL.md`: ten-rule cap, voice vs tone, Diego voice note — em dashes optional; fail stacking, not the mark.
- Dogfood copies under `.grok/skills/` match `skills/`.
- Rewrote [QUICK_START.md](./QUICK_START.md) for a clean-machine install (<5 min) with paths that exist in this repo.
- Updated [docs/DEPTH_MATRIX.md](./docs/DEPTH_MATRIX.md): 3 melted, 6 stub skills, 1 stub agent. No Claude inventory counts.
- Suite footers on README, QUICK_START, and AGENTS.md now link Reality OS plus the sibling Libre*-Grok-Build packs.
- README links [SECURITY.md](./SECURITY.md) and the Reality OS quality ladder. This pass targets L3–L4 hygiene; it does not claim L5.

## [0.0.1] — 2026-09-19

### Added

- Public scaffold for LibreCopy-Grok-Build (v0 stubs).
- Stub SKILL.md for first skills + suite orchestrator agent.
- README, LICENSE (MIT), GOLD_HAT, QUICK_START, CONTRIBUTING, SECURITY.
- Depth matrix + melt rules docs.

### Notes

- Honest stubs — not fake upstream depth counts. Melt next.
