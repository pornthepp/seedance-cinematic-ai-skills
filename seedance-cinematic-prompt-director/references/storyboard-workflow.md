# Seedance Storyboard Workflow

Use this for sequences longer than one clip.

## Split Rule

Split a scene when:

- The location changes.
- The emotional beat changes.
- The action has more than one major move.
- A camera cut would improve clarity.
- The requested duration exceeds a focused short clip.

## Character Consistency

Define the character once:

```text
Character:
Appearance:
Clothing:
Distinguishing features:
Reference use:
```

Then reuse the same keywords in every shot. Do not rewrite the same character differently in each prompt.

## Continuity Anchors

Track:

- Clothing, hair, injuries, props.
- Screen direction and entrance/exit.
- Lighting and time of day.
- Emotional state from the end of the previous shot.
- Environment and object placement.
- Sound bed or ambience.
- Shot size rhythm.

## Shot Rhythm

Vary shot size and energy:

- Wide -> close -> wide for breathing room.
- Static -> moving -> static for emphasis.
- Quiet -> loud -> quiet for contrast.
- Long -> short -> long for pacing.

Avoid repeating the same shot size, camera move, or energy across every shot.

## Storyboard Table

| Shot | Duration | Beat | Camera | Continuity From Previous | Final Prompt |
|---|---:|---|---|---|---|
| 1 |  |  |  |  |  |

## Per-Shot Format

```text
Shot [N] - [brief label]
Duration:
Continuity from previous:
Beat:
Final Seedance Prompt:
```
