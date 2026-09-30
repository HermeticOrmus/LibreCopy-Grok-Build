# Stubs

A stub is a thin cue: a name, a one-line job, and five steps. It is a reminder, not a playbook, so nothing here installs. Each stub names the pack plugin that holds the real depth, and that plugin installs from this repo's marketplace.

| Stub | Job | Real depth (pack plugin) | Install |
|------|-----|--------------------------|---------|
| [readme-engineering](./readme-engineering/SKILL.md) | README structure (Diátaxis-aware) | [`readme-engineering`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/readme-engineering) | `grok plugin install readme-engineering@libre-copy-grok --trust` |
| [runbook-writing](./runbook-writing/SKILL.md) | Incident / ops runbooks | [`runbook-writing`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/runbook-writing) | `grok plugin install runbook-writing@libre-copy-grok --trust` |
| [changelog-discipline](./changelog-discipline/SKILL.md) | CHANGELOG + semver honesty | [`changelog-management`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/changelog-management) | `grok plugin install changelog-management@libre-copy-grok --trust` |
| [error-messages](./error-messages/SKILL.md) | Actionable error UX | [`error-messages`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/error-messages) | `grok plugin install error-messages@libre-copy-grok --trust` |
| [tutorial-creation](./tutorial-creation/SKILL.md) | Tutorial sequencing | [`tutorial-creation`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/tutorial-creation) | `grok plugin install tutorial-creation@libre-copy-grok --trust` |
| [anti-slop](./anti-slop/SKILL.md) | AI-doc tells | None one to one. Nearest: [`style-guides`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/style-guides) and [`documentation-testing`](https://github.com/HermeticOrmus/LibreCopy-Claude-Code/tree/main/plugins/documentation-testing); the pack points slop sweeps at [markdown-discipline-skills](https://github.com/HermeticOrmus/markdown-discipline-skills), which is not in this marketplace | `grok plugin install style-guides@libre-copy-grok --trust` |

Also here: [librecopy-core/](./librecopy-core/), the v0 plugin bundle stub. It had no manifest and installed only a copy of the stub orchestrator. It is kept as the record; [plugins/libre-copy-grok](../plugins/libre-copy-grok/) replaces it.

The suite agent [AGENTS/copy-orchestrator.md](../AGENTS/copy-orchestrator.md) is also a stub coordinator. It stays where [AGENTS.md](../AGENTS.md) points, and nothing installs it: you merge it by hand.

## Melt a stub

1. Write the skill to the melted bar in [docs/MELT_RULES.md](../docs/MELT_RULES.md): when to use, steps, measurable checks, a worked example, an output shape.
2. `git mv stubs/<name> plugins/libre-copy-grok/skills/<name>`, drop the stub line, and give the frontmatter a routing description (`Use when ...`).
3. Copy it to `.grok/skills/<name>/SKILL.md` (CI checks the copy matches).
4. Update [docs/DEPTH_MATRIX.md](../docs/DEPTH_MATRIX.md), this table, and the README skills table.

The dogfood copies of these stubs in `.grok/skills/` match the files here, so a session opened in this repo sees them described as stubs.
