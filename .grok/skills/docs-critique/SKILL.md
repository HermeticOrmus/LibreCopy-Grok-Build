---
name: docs-critique
description: Critique one doc page for honesty, first success, runnable examples, and leftover stubs. Use when reviewing a README, API page, or runbook.
---

# Docs Critique

Daily critique loop for a single page. Truth over flattery. Measurable findings beat adjectives.

Gold Hat: teach the *why* of each finding. A critique that only lists defects extracts attention; a critique that leaves a reusable rule empowers the next page.

## When to use

- After a non-trivial docs change
- When asked to "look at this README / API page / runbook"
- Before calling a page shippable

Use `api-docs` first if the integrator job or first-success path is unnamed. Use `style-guide` (melted) for voice and the em-dash note. Use `anti-slop`, `readme-engineering`, `tutorial-creation`, `runbook-writing`, `error-messages`, and `changelog-discipline` (stubs) for leftover passes — call the stub; do not invent its depth.

Do not invent a numeric quality score. Severity ranks are enough.

## Operating steps

1. **Restate the reader job** in one line (who, task, first success). If unknown, infer from the page and say you inferred it.
2. **Walk the dimensions** below. For each finding: location (heading or line), current text, why it fails, exact remediation.
3. **Rank by severity.** Critical → high → medium → low. Cap the first patch list at what a person can do in one sitting.
4. **Name strengths** only when they are real (a working first curl, an honest status line). Do not pad.
5. **Hand off leftovers** to the matching stub skill instead of writing a fake full-suite audit.

Stop if you cannot name the reader job. Ask. Guessing an audience is extraction.

## Dimensions

### Honesty

Does the page claim only what this tree has? Status, depth counts, and "complete" are facts or they are lies.

Look for: Claude plugin/agent/command totals pasted as this repo's inventory, "world-class" with no evidence, unpublished paths, `/path/to/` that no one can run.

### First success

Can a stranger finish one real task without leaving the page? Install, auth, or the one command — then an expected result.

Look for: feature catalogs with no path, "see the docs" pointing at itself, missing prereqs.

### Examples that run

Copy-paste-run, or marked as unverified. Placeholders (`$API_TOKEN`, `~/project`) — never live secrets.

Look for: `example.com` bodies that are the word `"string"`, commands that assume undeclared tools, output that cannot match today's version.

### Diátaxis mix

One page, one quadrant. Tutorial, how-to, reference, and explanation do not share a heading stack.

Look for: a reference table that suddenly teaches onboarding; a tutorial that dumps every field.

### Error and next step

When the happy path fails, does the page name the failure and the next action?

Look for: "Invalid request" with no field; no `request_id`; blame ("you forgot") instead of a fix.

### Voice (tells, not taste)

Adjective stacks, soft closes, empty catalogs, and *indiscriminate* dash stacking are tells. One em dash is not a fail — see `style-guide`.

Look for: "powerful, comprehensive, seamless"; "Happy documenting!"; three bullets that say nothing.

### Freshness and links

Last-verified date or version pin when the page can rot. Internal anchors resolve. External URLs you did not fetch are **unverified**.

Do not invent a link status. If you did not check, say **unverified**.

### Secrets

No real tokens, cookies, or private URLs in examples or screenshots.

## Severity

| Rank | Meaning | Example |
|------|---------|---------|
| Critical | Blocks the job, or a false claim / leaked secret | Install command that cannot run; "20 plugins" claimed for a stub pack |
| High | Reader will bounce or mistrust | No first-success path; examples marked as if they run but cannot |
| Medium | Mix, drift, or missing next step | Tutorial dumped into reference; error with no action |
| Low | Polish | Extra blank lines; one soft close after a solid page |

If unsure between two ranks, pick the higher and say why.

## Worked example — weak landing

Job: a developer evaluates whether to install this API client. First success: one authenticated request returns 200.

Weak:

```markdown
# Acme API

A powerful, comprehensive, world-class platform.

## Features
- Fast
- Secure
- Easy

Just paste your key and go.
```

Critique (abridged):

```markdown
## Job
Evaluator runs one authenticated call. First success: HTTP 200 with a real resource id.

## Findings
1. **Critical — honesty.** "World-class" and a three-word feature catalog claim nothing measurable. Remediation: one-sentence purpose + honest status (what works now).
2. **High — first success.** No install, no auth, no expected body. Remediation: one curl with `$API_TOKEN` and the JSON they should see.
3. **High — examples.** "Just paste your key" invites a live secret into the page. Remediation: `$API_TOKEN` from the environment; never a sample that looks real.
4. **Medium — voice.** Adjective stack + empty catalog + soft close. Remediation: cut the triad; name one job.

## Strengths
The title names the product.

## Fixes now
1. Replace the hero with purpose + honest status.
2. Add auth + one runnable curl + expected 200 body.
3. Point leftover changelog / error-catalog work at the stub skills.

## Leftovers
Slop-only pass → `anti-slop` (stub). Full tutorial sequence → `tutorial-creation` (stub).
```

That is a critique: locations, severity, remediations, leftovers. Not a `/10` scorecard.

## Output shape

```markdown
## Job
[who / task / first success]

## Strengths
- [only real ones]

## Findings (severity-ranked)
1. **[Critical|High|Medium|Low] — [dimension].** [where] [what] [why]
   Remediation: [exact change]
2. …

## Fixes now
1. …
2. …
3. …

## Leftovers
- [skill] — [what you did not pretend to finish]
```

## Quality bar

A pass is done when every finding is specific, ranked, and remediable, and the teach-while-fixing sentence is implicit in the *why*. Refuse vibe-only notes ("make it punchier", "more professional") — translate them through `style-guide` or drop them.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/README.md).
