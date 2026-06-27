# Retake Protocol — The Iteration Economy

What happens after a generation comes back. This governs the partially good
take, which is most of real production.

## Triage Every Take — Five Verdicts

| Verdict | When | Next move |
|---|---|---|
| **Keep** | The primary purpose of this shot is delivered and nothing is fatal. | Lock it, log it, move on. Perfection in secondary details is post's job. |
| **Fix in post** | The flaw lives in post's domain: color, text, sound mix, trim, unstable frames at ends. | Never burn takes on what an editor fixes in minutes. |
| **Edit, don't regenerate** | Composition and timing are right; exactly one layer is wrong, and the surface supports edit. | Preserve the take as source; change only the failing layer. |
| **Re-roll** | The prompt is right; the sample was unlucky (sampling variance). | Same prompt, new seed. Two or three re-rolls maximum — then the prompt is the problem. |
| **Rewrite** | The same flaw appears in two or more takes. | It is systematic, not luck. Diagnose by mechanism, change the prompt. |

## The One-Variable Rule

Change one thing per retake:
- one prompt clause, OR
- the seed, OR
- the mode, OR
- one reference

Never change several at once. Same seed + one prompt change is the closest
thing to a controlled experiment. New seed + same prompt is a pure re-roll.
Change two things at once and the result is unreadable — you learn nothing.

## Attempt Budget

Set it before take one:
- Default: 5 standard-tier takes, or 10 fast-tier drafts
- Write a "good enough" definition: the primary purpose delivered,
  secondary flaws postable
- At half the budget with no progress on the same flaw, stop iterating
  and change strategy

## Diagnosis Flow

1. Is the flaw in the primary purpose or secondary detail?
2. If secondary → Fix in post or ignore
3. If primary → Did it appear in 2+ takes?
4. If yes → Rewrite (it's systematic)
5. If no → Re-roll once more, then rewrite if it persists
6. When rewriting, identify which mechanism is causing the failure
   (see model-mechanics.md)
