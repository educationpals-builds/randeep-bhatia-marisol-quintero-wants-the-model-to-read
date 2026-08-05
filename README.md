# Subrogation Recovery Estimate Checker

A task-fit checker for Marisol Quintero's request: have a model read each subrogation file and estimate how much money can be clawed back from the third-party carrier, with those estimates feeding next year's recovery forecast due in July.

---

## The problem this checker solves

Marisol Quintero, CFO, has to defend a recovery forecast she currently builds from adjuster guesses. She wants to hand the estimation task to a model—but before that happens, someone needs to decide whether the task actually fits.

This checker runs any "should AI do this?" question through five dials and returns a verdict, the deciding dial, a flip condition, and the smallest reshape that would make the task safer or more useful.

---

## How this checker was built

The builder worked through Marisol's actual task—subrogation recovery estimation—and recorded every judgment along the way. That run is now embedded as the checker's worked example, so it reads new tasks the way its builder reads them.

---

## The builder's worked example

### The task, as it was actually asked for

Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast.

### Who wants it handed over, and what they gain

Marisol Quintero, CFO, who has to defend a recovery forecast she currently builds from adjuster guesses

### What the verdict decides

Which recovery number goes into next year's plan — and therefore what my team is measured against all year

### When you must call it

July planning cycle, first pass due June 20

### The task restated as text-in, text-out

Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.

### Five dial ratings

| Dial | Rating (0–4) |
|------|--------------|
| Fits in text | 4 |
| Works one token at a time | 2 |
| Nothing to look up or remember | 3 |
| Someone can check the output | 4 |
| A confident wrong answer is survivable | 2 |

### The deciding dial

A confident wrong answer is survivable

### The plausible wrong answer, and who catches it

Model reads a well-argued but weak liability case as strong and outputs a high recovery number that inflates the forecast Marisol presents to the board.

### The verdict

Use it to draft the estimate on every file, but require a human sign-off on any file above $50k before it enters the forecast.

### What change would flip this read

If claims adjusters start rubber-stamping the model's number without reading the file themselves, the check stops being real and I'd pull it back to manual-only for large files.

### The smallest reshape

Have the model show which clauses or prior settlements it based the estimate on, so the adjuster can check the reasoning in under two minutes instead of rereading the whole file.

---

## One-paste rebuild block

To rebuild this checker from scratch, paste the following into a new session:

```
Task: Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast.

Who wants it: Marisol Quintero, CFO, who has to defend a recovery forecast she currently builds from adjuster guesses

What it decides: Which recovery number goes into next year's plan — and therefore what my team is measured against all year

Deadline: July planning cycle, first pass due June 20

Run the five dials. Return: verdict, deciding dial, plausible wrong answer with catcher, flip condition, smallest reshape.
```

---

## Related files

- [charter.md](charter.md) — Full audit of the subrogation recovery task
- [METHOD.md](METHOD.md) — The five-dial framework
- [VERIFY.md](VERIFY.md) — How to verify the checker works

<!-- educationpals-build-verified -->
