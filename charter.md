# Subrogation Recovery Estimate Checker — Full Audit

This charter documents the complete fit assessment for using a language model to read subrogation files and estimate recoverable amounts for Marisol Quintero's July planning forecast.

---

## The Task, Pinned

**What was asked:**  
Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast.

**Who wants it:**  
Marisol Quintero, CFO, who has to defend a recovery forecast she currently builds from adjuster guesses

**What this verdict decides:**  
Which recovery number goes into next year's plan — and therefore what my team is measured against all year

**Deadline:**  
July planning cycle, first pass due June 20

---

## The Task as Text-In, Text-Out

Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.

---

## The Five Dial Ratings

| Dial | Rating (0–4) |
|------|--------------|
| Fits in text | 4 |
| Works one token at a time | 2 |
| Nothing to look up or remember | 3 |
| Someone can check the output | 4 |
| A confident wrong answer is survivable | 2 |

---

## The Deciding Dial

**a_confident_wrong_answer_is_survivable** — rated 2

This dial decides the verdict because a confident wrong guess on a high-value file flows directly into the forecast Marisol presents to the board. The model can sound certain while misreading liability strength, and that error compounds when it lands in a planning number the team is measured against all year.

---

## The Plausible Wrong Answer

Model reads a well-argued but weak liability case as strong and outputs a high recovery number that inflates the forecast Marisol presents to the board.

---

## The Verdict

Use it to draft the estimate on every file, but require a human sign-off on any file above $50k before it enters the forecast.

---

## Flip Condition

If claims adjusters start rubber-stamping the model's number without reading the file themselves, the check stops being real and I'd pull it back to manual-only for large files.

---

## The Smallest Reshape

Have the model show which clauses or prior settlements it based the estimate on, so the adjuster can check the reasoning in under two minutes instead of rereading the whole file.

---

## Task Stream

Batch of subrogation files uploaded weekly from claims; model outputs a recovery estimate and rationale per file for adjuster review before the forecast roll-up.

---

## Summary

This checker is greenlit as a drafting tool with a $50k threshold checkpoint. Files above that threshold require adjuster sign-off before the estimate enters the July forecast. The reshape — surfacing the clauses and prior settlements behind each estimate — makes that review fast enough to be real.
