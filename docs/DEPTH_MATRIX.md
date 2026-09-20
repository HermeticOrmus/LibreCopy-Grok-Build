# Depth matrix

Update this table when melting. Status words mean what they say:

| Status | Meaning |
|--------|---------|
| stub | Thin cue only. Usable as a reminder, not a playbook. |
| melted | Real Grok skill: when-to-use, steps, measurable checks, example, output shape. |

Never copy Claude plugin / agent / command totals into this inventory. Upstream [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code) is proof that the *job* exists, not a count this repo has earned.

| ID | Kind | Status | Source (Claude, for melt) | Notes |
|----|------|--------|---------------------------|-------|
| docs-critique | skill | melted | plugins/documentation-testing + content-strategy | New Grok skill. Dimensions, severity, remediations. No `/10` card. |
| api-docs | skill | melted | plugins/api-documentation | API narrative: job, auth, first success, error they will hit. Not a full OpenAPI lint. |
| style-guide | skill | melted | plugins/style-guides | Ten-rule cap. Diego voice: em dashes optional; fail stacking, not the mark. |
| readme-engineering | skill | stub | plugins/readme-engineering | Diátaxis landing cue only. |
| runbook-writing | skill | stub | plugins/runbook-writing | Trigger / rollback cue only. |
| changelog-discipline | skill | stub | plugins/changelog-management | Semver cue only. |
| error-messages | skill | stub | plugins/error-messages | Next-step cue only. |
| tutorial-creation | skill | stub | plugins/tutorial-creation | Sequence cue only. |
| anti-slop | skill | stub | Claude README tells + markdown-discipline companion | Tell list only. |
| copy-orchestrator | agent | stub | suite coordinator (no 1:1 Claude agent) | Coordinates the skills; not a melted specialist. |

This repo now: **3 melted skills**, **6 stub skills**, **1 stub agent**.

Dogfood copies of every skill live at `.grok/skills/<id>/SKILL.md` and must match `skills/<id>/SKILL.md`.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Sibling Libre*-Grok-Build packs: [README suite footer](../README.md).
