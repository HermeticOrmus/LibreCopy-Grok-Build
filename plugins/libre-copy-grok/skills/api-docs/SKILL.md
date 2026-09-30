---
name: api-docs
description: API narrative — job-first getting started, auth, one runnable example, error catalog, change policy. Use when writing or repairing API docs.
---

# API Docs

Write the *narrative* of first success, then the reference that stays true. These are observations about how integrators learn — not a renderer, not a score.

Gold Hat: name the integrator job first, then teach the beat while you fix the page. Leave the person able to document the next endpoint without you.

## When to use

- A new API, SDK, or webhook needs a getting-started path
- Auth or examples are the bounce
- Reference exists but no stranger can finish one call
- You are asked for "API docs" or "API narrative"

Do not use this skill as a full OpenAPI lint, a changelog rewrite, or an in-product error-UX pass. After the narrative is named, hand to `docs-critique` (structure + honesty; melted) and to `error-messages` / `changelog-discipline` / `tutorial-creation` (stubs). Call the stub; do not invent its depth.

## Operating steps

1. **Name the job.** Who integrates, what they must accomplish, what "it worked" looks like (status + one field).
2. **Write the spine.** Auth → first success call → the error they will actually hit → what to read next. One page. No catalog yet.
3. **Walk the beats** below. Record only findings you can point at (heading + current text + beat).
4. **Propose three concrete fixes** (or fewer if the page already works). Each fix names the beat it serves.
5. **Teach one sentence.** Why this change, in language the next writer can reuse.

Stop if you cannot name the integrator job. Ask. Guessing a first call is extraction.

## Beats (measurable)

### Auth (highest bounce)

Auth is the page people leave. Spend disproportionate effort. Show every method you actually support. Placeholders only (`$API_TOKEN`).

| Check | Pass | Fail |
|-------|------|------|
| Method named | Bearer / API key / OAuth — whichever is real | "Authenticate" with no header |
| Copy-paste | One command that fails closed if the var is empty | A key that looks live (`sk_live_…`) |
| Failure | 401 body + next step (rotate, scope, clock) | "Unauthorized" and nothing else |

### First success

One call. Expected status. One field the reader can see in the body (id, status, location).

| Check | Pass | Fail |
|-------|------|------|
| Runnable | curl or SDK snippet with declared tools | "Call POST /orders" with no body |
| Expected | `201` + `id` (or equivalent) shown | "You should see a response" |
| Scope | One happy path | Every optional field in the first sample |

### Error they will hit

The first failure is usually validation, auth, or 404 — not 500. Document the structured body and the action.

```json
{
  "code": "VALIDATION_ERROR",
  "message": "line_items must contain at least one item",
  "errors": [{ "field": "line_items", "code": "MIN_LENGTH" }],
  "request_id": "req_a8f3"
}
```

`request_id` is how support finds the request. "Invalid request" is not a catalog.

| Check | Pass | Fail |
|-------|------|------|
| Code + action | Named code and what to change | Generic 400 text |
| Example | Realistic field path | `"string"` / `"email@example.com"` only |

### Diátaxis

```
                  Action            Reflection
  Practical   | Tutorial    | How-to guide |
  Theoretical | Reference   | Explanation  |
```

Mix at your peril. The grid is [diataxis.fr](https://diataxis.fr). Getting started is a tutorial or a how-to. Field tables are reference. Do not dump the field table into the first-success page.

### Change policy

Breaking changes first. User-facing Added / Changed / Fixed. No vanity refactors in the customer log.

Hand the full changelog shape to `changelog-discipline` (stub). Here: one paragraph that says how you version (URL `/v2` vs `Accept` header) and where breaking changes are announced.

### Examples that stay true

Realistic ids (`usr_01HX…` style), ISO timestamps, amounts in the unit you actually use (cents vs decimal — say which). Multiple examples (minimal / full / edge) belong in reference, not in the first-success spine.

If you did not run the snippet against a spec or a server, mark it **unverified**.

## Problem → beat → fix

| Complaint | Beat | First fix |
|-----------|------|-----------|
| "I bounced on auth" | Auth | One header example + 401 next step |
| "The example doesn't run" | First success | One curl, expected status + id |
| "Errors are useless" | Error they will hit | Structured code + field + `request_id` |
| "I can't find anything" | Diátaxis | Split tutorial spine from reference table |
| "Docs lie after a release" | Change policy | Breaking changes first; pin the version in the URL |

## Worked example — first order

Job: a backend engineer creates one order. First success: `201` and an `id`.

Weak:

```markdown
# Orders

POST /orders creates an order.

Example: `{ "items": "string" }`
```

Stronger (beat-tagged):

````markdown
# Create your first order

## Auth

```bash
curl -sS https://api.example.com/v2/orders \
  -H "Authorization: Bearer $API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"items":[{"product_id":"prod_demo","quantity":1}]}'
```

Expected: `201` with `"id": "ord_…"` and `"status": "created"`.

If you get `401`, the token is missing or expired — mint a new one; do not paste it into the doc.

## When it fails

`422` + `VALIDATION_ERROR` on `items` means the array was empty. Add one item. Send `request_id` if you ask for help.

## Next

Reference for every field. Webhook signature how-to. Not this page.
````

- **Auth:** Bearer + `$API_TOKEN`. No live key.
- **First success:** one curl, `201`, `id` + `status`.
- **Error they will hit:** `422` on empty `items`, plus `request_id`.
- **Diátaxis:** next links out; the field encyclopedia stays in reference.

Three concrete fixes if you only have the weak page: (1) replace `"string"` with a minimal valid body, (2) show auth and the expected `201`, (3) document one validation error — then run `docs-critique` for honesty and `error-messages` (stub) for in-product copy.

## Output shape

```markdown
## Job
[who / task / first success]

## Spine
1. Auth — [pass/fail]
2. First success — [pass/fail]
3. Error they will hit — [pass/fail]
4. Next — [where]

## Findings
- [beat] — [heading] — [current] → [needed]

## Fixes (≤3)
1. [change] — serves [beat]
2. …
3. …

## Teach
[one reusable sentence]
```

If the spine already works, say so. Empty findings are allowed. Invented issues are not.

## Suite

Doctrine: [grok-build-reality-os](https://github.com/HermeticOrmus/grok-build-reality-os). Gold Hat: [GOLD_HAT.md](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/GOLD_HAT.md). Sibling Libre*-Grok-Build packs: [README suite footer](https://github.com/HermeticOrmus/LibreCopy-Grok-Build/blob/main/README.md).
