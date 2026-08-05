# Subrogation Recovery Estimation — Five-Dial Prompt Pack

Five standalone prompts for evaluating whether AI should handle subrogation file recovery estimation. Each prompt checks one dial. Paste any task description into any chat model alongside the prompt.

---

## Prompt 1: Fits in Text

```
I need to evaluate whether a task fits well in text form for AI processing.

Here is the task:
[PASTE TASK DESCRIPTION HERE]

Evaluate this task on the "Fits in Text" dial (0–4 scale):
- 4 = The task is entirely text-based; all inputs and outputs are naturally expressed as text
- 3 = Mostly text, with minor non-text elements that can be described
- 2 = Mixed; significant information lives outside text
- 1 = Primarily non-text; text is a poor substitute
- 0 = Cannot be meaningfully expressed in text

First, restate the task as text-in, text-out: what token stream goes in, what comes out, and what the task assumes the model holds on its own.

Then give your rating (0–4) with a one-line reason.

Example calibration:
Task: "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
Text-in/text-out: Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.
Rating: 4 — The subrogation files are already text documents; the output is a number and short explanation, both naturally text.
```

---

## Prompt 2: Works One Token at a Time

```
I need to evaluate whether a task works well with sequential token-by-token generation.

Here is the task:
[PASTE TASK DESCRIPTION HERE]

Evaluate this task on the "Works One Token at a Time" dial (0–4 scale):
- 4 = Output flows naturally in sequence; no need to revise earlier tokens based on later reasoning
- 3 = Mostly sequential; occasional backtracking would help but isn't critical
- 2 = Mixed; the task benefits from iteration or revision
- 1 = Heavily iterative; good output requires substantial revision
- 0 = Cannot produce quality output without extensive back-and-forth

First, restate the task as text-in, text-out: what token stream goes in, what comes out.

Then give your rating (0–4) with a one-line reason.

Example calibration:
Task: "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
Text-in/text-out: Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.
Rating: 2 — Estimating recovery requires weighing multiple factors (liability strength, policy limits, prior settlements) that interact; the model may need to revise its estimate as it reasons through the file.
```

---

## Prompt 3: Nothing to Look Up or Remember

```
I need to evaluate whether a task requires external lookups or persistent memory.

Here is the task:
[PASTE TASK DESCRIPTION HERE]

Evaluate this task on the "Nothing to Look Up or Remember" dial (0–4 scale):
- 4 = Everything needed is in the prompt; no external data or memory required
- 3 = Minor external context would help but isn't essential
- 2 = Moderate need for external data or cross-session memory
- 1 = Significant reliance on lookups or remembering prior interactions
- 0 = Cannot function without real-time data access or persistent memory

First, restate the task as text-in, text-out: what token stream goes in, what comes out, and what the task assumes the model holds on its own.

Then give your rating (0–4) with a one-line reason.

Example calibration:
Task: "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
Text-in/text-out: Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.
Rating: 3 — The file text is provided, but accurate estimation benefits from knowing typical settlement ranges, carrier behavior patterns, and jurisdiction-specific recovery rates that aren't in the file itself.
```

---

## Prompt 4: Someone Can Check the Output

```
I need to evaluate whether a task's output can be verified by a human.

Here is the task:
[PASTE TASK DESCRIPTION HERE]

Evaluate this task on the "Someone Can Check the Output" dial (0–4 scale):
- 4 = Output is easily verified; a reviewer can confirm correctness quickly
- 3 = Verification is straightforward but takes some effort
- 2 = Checking requires expertise or significant time
- 1 = Verification is difficult; errors may go unnoticed
- 0 = Output cannot be meaningfully checked before use

First, restate the task as text-in, text-out: what token stream goes in, what comes out.

Then give your rating (0–4) with a one-line reason.

Example calibration:
Task: "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
Text-in/text-out: Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.
Rating: 4 — An adjuster can read the rationale and compare it against the file to see if the estimate makes sense; the reasoning is exposed, not hidden.
```

---

## Prompt 5: A Confident Wrong Answer Is Survivable

```
I need to evaluate whether a task can tolerate a confident but incorrect AI output.

Here is the task:
[PASTE TASK DESCRIPTION HERE]

Evaluate this task on the "A Confident Wrong Answer Is Survivable" dial (0–4 scale):
- 4 = Wrong answers are caught easily and cause minimal harm
- 3 = Errors are recoverable with some cost or delay
- 2 = Confident wrong answers could cause real damage if not caught
- 1 = Errors are costly and may not be caught in time
- 0 = A confident wrong answer could be catastrophic

First, restate the task as text-in, text-out: what token stream goes in, what comes out.

Then describe the plausible wrong answer: what fluent-but-incorrect output might the model produce, and who catches it (or state plainly if nobody would)?

Then give your rating (0–4) with a one-line reason.

Example calibration:
Task: "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
Text-in/text-out: Input: subrogation file text (claim notes, policy terms, prior settlements). Output: a dollar estimate plus a short rationale, per file.
Plausible wrong answer: Model reads a well-argued but weak liability case as strong and outputs a high recovery number that inflates the forecast Marisol presents to the board.
Rating: 2 — A confident overestimate on high-value files flows into the annual forecast and sets targets the team gets measured against all year; the error compounds rather than self-corrects.
```

---

## Using This Pack

1. Copy one prompt into any chat model
2. Replace `[PASTE TASK DESCRIPTION HERE]` with the task you're evaluating
3. Review the rating and reasoning
4. Repeat for all five dials to get a complete fit read

After running all five dials, use the ratings to make your call:
- Which dial scored lowest? That's likely your deciding dial.
- If "A Confident Wrong Answer Is Survivable" scores 2 or below, consider a human checkpoint on high-stakes outputs.

---

## Sample Asks

Paste these task descriptions to test the prompts:

- "Read each subrogation file and estimate the recoverable amount from the third-party carrier, producing a number per file for the forecast."
- "Review claim notes and flag files where liability is disputed by the third-party carrier."
- "Summarize prior settlement history for each open recovery case."
