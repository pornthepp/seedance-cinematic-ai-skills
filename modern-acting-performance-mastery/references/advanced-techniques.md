# Advanced Acting Direction

Beyond basic objective-obstacle-tactic. Patterns for directing nuanced performances and avoiding common AI direction failures.

## The AI Direction Problem

AI models (including the one reading this skill) have specific failure patterns when directing performance. Understanding these prevents them.

### Failure 1: Emotion Labeling Instead of Behavior

**The pattern:** "She feels a mix of anger and sadness, conflicted between her loyalty to her family and her desire for freedom."

**Why it fails:** This describes internal psychology, not playable behavior. An actor cannot perform "a mix of anger and sadness." They can perform specific actions that produce that reading in the audience.

**Fix template:**

```text
Instead of: "She feels [emotion]."
Write: "She [visible action] — [specific physical behavior]. 
Her [body part] [does what]. She [playable verb] by [method]."
```

**Example:**

```text
Wrong: "She feels conflicted between anger and sadness."

Right: "She grips the edge of the table with both hands — her knuckles 
whiten. She opens her mouth to speak, then closes it. She looks at her 
mother, holds eye contact for two seconds, then looks down at her own 
hands. When she finally speaks, her voice is steady but too quiet — she 
is controlling it so tightly that the effort is visible in her jaw."
```

### Failure 2: Symmetrical Dialogue Direction

**The pattern:** Directing both characters in a conversation the same way — same energy level, same emotional register, same tactical approach.

**Why it fails:** Real conversations are asymmetric. One person wants something the other does not want to give. One person is performing while the other is genuine. One person is escalating while the other is retreating.

**Fix:** Before directing any dialogue scene, answer:

1. Who has more power right now? (Not always the one speaking.)
2. Who is performing and who is authentic?
3. Who is advancing and who is defending?
4. What would each character do if the other suddenly stopped talking?

The answers should be different for each character. If they are the same, the scene has no tension.

### Failure 3: Over-Directing Listening

**The pattern:** Describing exactly what the listening character's face does during every line of the speaking character's dialogue. "As he says X, she furrows her brow. As he says Y, she bites her lip."

**Why it fails:** Over-directed listening looks choreographed. Real listening is messier — people look away, touch their face, shift weight, think about what they are going to say next, miss what was just said because they were composing their response.

**Fix:** Direct listening in broad strokes, not beat-by-beat:

```text
"While he talks, she is composing her counter-argument. She is only 
half-listening — she already knows where this is going. Her eyes move 
between his face and the door. When he says the one thing she did not 
expect, she stops moving entirely."
```

The key: listening direction should name what the character is DOING internally (composing a response, waiting for it to end, looking for an exit, being genuinely surprised) not what their face looks like.

## The Mask and The Leak

The most powerful performance tool for complex characters. Every person in every social situation wears a mask — a controlled presentation. The truth leaks through in moments they cannot control.

### How To Direct The Mask

The mask is the character's chosen behavior — what they want the world to see:

- The composed professional
- The caring parent
- The casual friend who is not jealous
- The confident leader who is not afraid
- The calm person who is not furious

Direct the mask as a **performance within the performance.** The character is acting. They are choosing their words, controlling their body, maintaining a social face.

### How To Direct The Leak

The leak is the truth escaping through the mask. It is involuntary, small, and specific:

- A jaw muscle clenching while smiling
- A hand finding a pocket or gripping an object when the voice stays calm
- A micro-pause before answering a question — the time it takes to compose the lie
- Breathing changing — faster, shallower, or a sudden deep breath that was not planned
- Eye contact breaking for half a second at the exact wrong moment
- Voice pitch shifting on one word — slightly higher (stress) or lower (suppression)

### The Ratio Rule

The ratio of mask-to-leak determines what the audience understands:

| Ratio | Audience Reading |
|---|---|
| 95% mask / 5% leak | The character is in control. The audience catches the tiny leak and feels smart for noticing. Sophisticated. |
| 80% mask / 20% leak | The character is struggling but maintaining. Tension between what they show and what they feel. |
| 50% mask / 50% leak | The mask is failing. The audience sees both the effort and the truth. Vulnerability. |
| 20% mask / 80% leak | The character has lost control but is still trying. Desperation. Breakdown. |
| 0% mask / 100% leak | The character has given up controlling their presentation. Surrender, confession, or collapse. |

**For AI video/image prompts:** Specify both the mask and the leak:

```text
"Her expression is a professional smile — polished, symmetrical, 
practiced. But her left hand, below the table where she thinks no one 
can see it, is gripping the fabric of her skirt. Her smile does not 
reach her eyes — the skin around her temples is tight."
```

## Status Transactions

Every interaction involves a status negotiation. Characters are constantly adjusting their status relative to each other — raising or lowering themselves through behavior.

### High-Status Behaviors

- Stillness. Moving less than the other person.
- Slow speech with pauses. Not rushing.
- Sustained eye contact. Not looking away first.
- Taking up space — wide stance, arms away from body, claiming furniture.
- Speaking last. Letting silence sit after the other person finishes.
- Touching objects casually — picking up someone else's belonging without asking.
- Controlled volume. Not needing to be loud.

### Low-Status Behaviors

- Fidgeting. Hands busy, weight shifting.
- Fast speech. Filling silence to prevent discomfort.
- Breaking eye contact. Looking down (submissive) or sideways (evasive).
- Making body smaller — arms close, shoulders forward, occupying less space.
- Speaking to fill silence. Not tolerating pauses.
- Asking permission. "Is it okay if...?" "Can I just...?"
- Apologizing for existing. "Sorry, I just..." "I know this is stupid, but..."

### The Status Dance

The most interesting scenes involve status shifts. A character who starts high and ends low (or vice versa) creates dramatic movement:

**Direction technique:** Assign a status number (1-10) to each character at the beginning and end of the scene. Then map the trajectory:

```text
Scene: Job interview
Character A (Interviewer): Starts at 8, ends at 5
Character B (Candidate): Starts at 3, ends at 7

What happens: The candidate knows something the interviewer doesn't. 
As the conversation progresses, the power shifts. The interviewer's 
certainty erodes. The candidate's body language opens up while the 
interviewer's closes down.
```

## Beat Mapping For Complex Scenes

A beat is the smallest unit of dramatic action — a moment where one tactic replaces another. Most AI-directed scenes have 2-3 beats. Professional scene work has 5-12.

### How To Find Beats

A new beat starts when:
- One character changes their tactic (from persuading to threatening).
- New information arrives (a phone rings, a fact is revealed).
- The balance of power shifts.
- One character makes a decision.
- The physical arrangement changes (someone stands, sits, moves closer, moves away).

### Beat Mapping Format

| Beat | Trigger | Character A Tactic | Character B Tactic | Status Shift | Physical Change |
|---|---|---|---|---|---|
| 1 | Scene starts | Charm (friendly, open) | Test (cautious, watching) | A:7 B:4 | A is standing, B is seated |
| 2 | A says something revealing | Recover (backpedal, laugh it off) | Press (lean forward, repeat the word) | A:5 B:6 | B sits up straighter |
| 3 | B asks the real question | Deflect (change subject, pour a drink) | Wait (silence, eye contact) | A:4 B:7 | A turns away to pour |
| 4 | A answers honestly | Expose (voice drops, stops moving) | Receive (body softens, looks away) | A:5 B:5 | Both are still. Equal. |

### The "No Empty Beats" Rule

Every beat must do at least one of these:
- Change the power balance
- Reveal new information
- Force a decision
- Alter a relationship

If a beat does not do any of these, it is an empty beat — the scene is treading water. Cut it or combine it with an adjacent beat.

## Physical Specificity Checklist

When writing performance direction (for actors or AI video prompts), check that you have specified:

- [ ] **Weight distribution.** Which foot carries the weight? Is the character leaning?
- [ ] **Hand state.** Where are the hands? Open, closed, holding something, hidden?
- [ ] **Breath pattern.** Normal, shallow, held, sighing, controlled?
- [ ] **Eye target.** Where are they looking? At the other person's eyes, mouth, hands? At an object? At nothing?
- [ ] **Jaw and mouth.** Clenched, relaxed, lip-biting, swallowing?
- [ ] **Spine.** Upright, slouched, rigid, curved forward?
- [ ] **Tempo.** Fast, slow, deliberate, impulsive, frozen?
- [ ] **Relationship to objects.** Are they touching, avoiding, arranging, or destroying something?

If more than three of these are unspecified, the performance will be generic. The body tells the story — not the face alone.
