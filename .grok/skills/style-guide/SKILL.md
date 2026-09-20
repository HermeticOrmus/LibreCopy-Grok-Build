---
name: style-guide
description: Voice, vocabulary, and formatting rules that people will actually follow. Use when setting or checking suite voice — including Diego voice and em dashes.
---

# Style Guide

Ten high-impact rules beat a hundred unread ones. Voice is constant. Tone moves with the page.

Gold Hat: teach the rule with a do/don't from *this* domain. A list of abstractions extracts compliance theater; a pair the next writer can reuse empowers them.

## When to use

- A pack or product needs a voice that will actually be followed
- Two pages disagree on person, tense, or product names
- Someone asks to "clean up the tone" or "add a style guide"
- You are writing examples and wondering about em dashes (see the optional note)

Use `docs-critique` for a page-level honesty/severity pass. Use `anti-slop` (stub) for a slop-only sweep. Use `api-docs` when the problem is narrative, not voice. Do not invent Vale coverage this repo does not ship.

## Operating steps

1. **Name the audience and the voice** in one line (who reads, what "sounds like us" means). If the project already has a base guide (Google, Microsoft), extend it — do not fork it.
2. **Pick at most ten rules.** If a rule is already in the base guide and you do not differ, link out. Write only differences and the terms your team gets wrong.
3. **Give every rule a do/don't** from this product. No orphan principles.
4. **Mark enforceability.** Vale / lint / PR checklist / writer judgment. Unenforced rules are reminders, not law.
5. **Teach one sentence.** Why this voice, in language the next editor can reuse.

Stop if you cannot name the audience. Ask.

## The ten-rule cap

A style guide with 100 rules is a style guide no one reads. Start from these seats; fill only what you will enforce:

1. Person (second vs third)
2. Tense (present vs future)
3. Voice (active vs passive)
4. Core terminology (3–5 terms this team misspells or relitigates)
5. Code in prose (backticks, language hints on fences)
6. Heading case (this suite: sentence case)
7. Inclusive substitutions you will actually automate
8. Tone by context (tutorial vs reference vs error vs advisory)
9. Numbers and dates
10. Contractions (always / never / by context)

Do not add an 11th rule about commas until the first ten hold.

## Voice vs tone

**Voice** does not change. This suite's voice is: truth-seeking, technically honest, teach-while-helping.

- Clear: ambiguity dies before the reader sees it.
- Direct: say the thing. No hedge stack.
- Technically honest: name limits, stubs, and unverified claims.

**Tone** changes with the job:

| Situation | Tone | Example |
|-----------|------|---------|
| Tutorial | Patient | "You have a `201`. Next you will verify the webhook." |
| API reference | Neutral | "Returns 404 if the resource does not exist." |
| Error | Action + no blame | "The API key expired. Generate a new one in the dashboard." |
| Breaking change | Direct | "Removed in v3. Use `client.connect()`." |
| Security advisory | Urgent | "Update now. 2.0–2.3 are vulnerable." |

## Optional: Diego voice and em dashes

Do not fail a page for using an em dash. Diego's voice (HermeticOrmus) uses them for parentheticals and turns. That is allowed.

The AI tell is *indiscriminate* dash stacking — every clause broken by the same tic. Flag the pattern, not the mark.

"No em dashes" is not a requirement in this pack. Examples may include em dashes. Companion repos that strip dashes as slop are optional, not law here.

Do:

```markdown
Auth is the bounce — spend the effort there.
```

Don't treat as a defect:

```markdown
Auth is the bounce. Spend the effort there.
```

Both are fine. Fail this instead:

```markdown
Auth is the bounce — and the page — if you skip it — will leak readers — fast.
```

That last line is a tic, not a voice.

## Do / don't (suite defaults)

| Rule | Do | Don't |
|------|----|-------|
| Person | "You run `curl`" | "The user should run `curl`" |
| Tense | "This command creates a file" | "This command will create a file" |
| Active | "The SDK throws `AuthError`" | "`AuthError` is thrown when…" |
| Headings | Sentence case (`## When to use`) | Title Case Every Word |
| Code | `` `GET /users/{id}` `` | Bare `GET /users/{id}` in prose without cues |
| Honesty | "2 melted, 6 stubs" | Claude totals as this repo's count |
| Close | Stop when the job is done | "Happy documenting!" |
| Secrets | `$API_TOKEN` | Live keys, cookies, private URLs |

Why active voice: the actor is what a debugger needs. Why sentence case: Reality OS markdown discipline. Why no soft close: the page already ended.

## Worked example — five rules, not fifty

Audience: integrators reading a public API pack. Voice: honest, second person, present tense.

```markdown
## Voice
Truth-seeking. Second person. Present tense. Active.

## Terms
- sign in (not log in)
- allowlist / blocklist (not whitelist / blacklist)
- SKILL.md (not "prompt file")

## Em dashes
Optional. Diego voice may use them. Fail stacking, not the mark.

## Enforce
- PR checklist: honest depth counts; no live secrets
- Vale: not shipped in this repo — do not claim it

## Out of scope
Oxford comma debates. Full Google guide (link it).
```

That is a shippable guide: audience, ten-or-fewer rules, do/don't implied, enforceability named, leftovers honest.

## Output shape

```markdown
## Audience / voice
[who] — [constant voice]

## Rules (≤10)
1. [rule] — Do: […] Don't: […] — Enforce: [vale|checklist|judgment]
2. …

## Diego / dashes
[optional | stacking flagged | not a hard fail]

## Leftovers
- [base guide link]
- [stub skill you did not fake]
```

If the existing guide already holds, say so. Empty additions are allowed. Invented house style is not.

## Quality bar

A pass is done when a stranger could apply the same ten rules without you, every rule has a domain example, and em dashes were not banned by accident. Refuse a 100-rule dump.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/README.md).
