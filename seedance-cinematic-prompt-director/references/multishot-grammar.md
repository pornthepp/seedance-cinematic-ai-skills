# Multi-Shot Grammar — Real Cuts Inside One Generation

Seedance 2.0 can produce 2–3 shots with genuine editorial cuts in a single
10–15s call. This is its defining capability over 1.x.

## The Grammar

Label every cut explicitly — `Shot 1:` / `Shot 2:` / `Shot 3:` — in plain
prose. The labels give the model cut points; long unlabeled prompts render as
one continuous take.

Per shot: **one primary action + one camera move**, plus sound.
Order inside each shot: subject + action → camera → sound.

## The Budget

Shots cost seconds. Plan ≈4–6s per shot:

| Shots | Recommended duration |
|---|---|
| 1 | 4–8s |
| 2 | 8–12s |
| 3 | 12–15s |

`duration: auto` lets the model size the clip to the prompt's complexity —
a strong default for multi-shot. Set explicit duration only when the edit
demands it.

## Requirements

- **Standard tier recommended.** Fast tiers may not reliably honor multi-shot,
  slow-motion, or dolly moves on the first try.
- **10–15s or `auto`.** Multi-shot below ~10s starves the beats.
- Ask for four shots in 5s and the model compresses or skips beats.

## Timestamps

Prefer `Shot N:` labels as the structure — clear and portable across surfaces.
Timestamp pacing phrases ("At 5 seconds…", "Cut scene to…") can be used
sparingly as hints inside a labeled shot, never as the primary structure.

**Surface exception — Dreamina/Jimeng:** Chinese community practice structures
longer prompts with a bracketed timeline:
`【時間軸】0-3s: … / 3-6s: … / 6-10s: …` — each segment carrying its own
frame/camera/sound. Match the convention of the active surface.

## Dialogue & Audio Placement

A spoken line goes inside the shot where the character delivers it.
Do not place dialogue between shots — it has no visual anchor.

## Example

```
Shot 1: A young woman in a dark coat pushes open a heavy wooden door.
Her breath fogs in the cold air. Camera: wide shot from inside, door
swings toward camera. Sound: door hinge creak, wind gust.

Shot 2: She steps into a candlelit hallway, pausing to look left.
Camera: medium tracking shot, following her from the side.
Sound: her footsteps echo on stone, candle flames flutter.

Shot 3: Close-up on her face as she sees something off-screen.
Her eyes widen, lips part slightly. Camera: slow push-in.
Sound: silence, then a distant bell toll.
```
