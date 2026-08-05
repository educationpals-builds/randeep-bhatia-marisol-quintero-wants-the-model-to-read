# Verifying the Subrogation Recovery Estimate Checker

This document explains how a stranger can confirm the checker works as built.

---

## What verification proves

A working checker does four things when you paste a subrogation-style task:

1. **Restates the task as text-in, text-out** — names what goes into the model and what comes out, plus any assumed data store
2. **Returns all five dial reads** — each dial gets a score and a one-line reason
3. **Names the deciding dial** — the one that tips the verdict
4. **Shows a flip condition and a reshape** — what would change the call, and the smallest buildable improvement

---

## How to verify

### Step 1: Paste a sample ask

Open the checker and paste a task like this:

> "We want the model to read subrogation files and estimate how much we can recover from the at-fault carrier. The estimates go into next year's budget forecast."

Or try a variation:

> "Can AI review our recovery case files and predict the dollar amount we'll collect from third-party insurers?"

### Step 2: Confirm the checker names the assumed store

The output should restate the task and call out what the model needs access to — for example:

- Subrogation file text (claim notes, policy terms, prior settlements)
- Any historical settlement data the task assumes the model "just knows"

If the checker doesn't name what's assumed, verification fails.

### Step 3: Confirm the checker returns a reshape

Every result must include a reshape move — a concrete, buildable change to the task. For the builder's specimen, the reshape was:

> Have the model show which clauses or prior settlements it based the estimate on, so the adjuster can check the reasoning in under two minutes instead of rereading the whole file.

Your test task should produce a similarly specific reshape — not "use better AI" or "add more data."

### Step 4: Confirm the $50k threshold logic appears

The builder's verdict gates high-value files through human review:

> Use it to draft the estimate on every file, but require a human sign-off on any file above $50k before it enters the forecast.

When you paste a task involving financial estimates that feed a forecast, the checker should surface whether a threshold checkpoint makes sense — and name who does the checking (in this case, adjusters).

---

## Verification checklist

| Check | Pass criteria |
|-------|---------------|
| Text-in, text-out restatement | Output names the input (file text) and output (dollar estimate + rationale) |
| Assumed store named | Output flags any data the task assumes the model holds on its own |
| Five dials scored | Each dial has a 0–4 rating and a reason |
| Deciding dial named | Output states which dial tips the verdict |
| Flip condition present | Output names a concrete change that would reverse the call |
| Reshape present | Output names a buildable improvement shippable this month |

If all six checks pass, the checker is working as built.

---

## What a failed verification looks like

- Output says "this is an AI task" without naming what goes in and out
- No dial scores, or scores without reasons
- Reshape is vague ("improve the model") instead of specific
- No mention of who catches a wrong answer or whether anyone does

If you see these, the checker needs repair before use.
