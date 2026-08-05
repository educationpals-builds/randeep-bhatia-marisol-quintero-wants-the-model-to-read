# The ATLAS Framework

This file documents the method behind the checker. The five-letter acronym appears only here.

---

## What ATLAS Stands For

**A** — A confident wrong answer is survivable  
**T** — Text fits in the context window  
**L** — Looks up nothing outside the prompt  
**A** — Answers one token at a time  
**S** — Someone can check the output  

---

## How the Dials Work

Each dial runs 0–4. The rating reflects how well the task fits that dimension:

| Score | Meaning |
|-------|---------|
| 0 | Hard no — the task fails this dimension outright |
| 1 | Weak fit — serious friction here |
| 2 | Mixed — workable with guardrails |
| 3 | Good fit — minor concerns only |
| 4 | Strong fit — no meaningful friction |

---

## The Deciding Dial

One dial decides the verdict. It's the dimension where a miss would hurt most, or where the task's fit is weakest relative to the stakes.

For Marisol Quintero's subrogation recovery estimate task, the deciding dial is **"A confident wrong answer is survivable"** — because a fluent but wrong recovery number could inflate the forecast she presents to the board.

---

## From Dials to Verdict

The checker doesn't average scores. It reads the pattern:

- If the deciding dial scores 0–1, the task stays human unless reshaped.
- If the deciding dial scores 2, the task can run with a named checkpoint.
- If the deciding dial scores 3–4, the task can run with lighter oversight.

The verdict always names the deciding dial and the checkpoint (if any).

---

## Flip Condition and Reshape

Every verdict includes:

1. **Flip condition** — the concrete change that would reverse the call.
2. **Reshape move** — the smallest change to the task itself that a team could ship this month.

These keep the verdict actionable. A stranger reading the output knows what would change the answer and what to try first.

---

## Why the Letters Stay Here

The checker's output never shows "ATLAS" or the dial letters. A stranger sees plain-language dial names, a verdict, and a reshape — not a framework brand. This file exists so the builder (and anyone auditing the method) can trace the logic back to its source.
