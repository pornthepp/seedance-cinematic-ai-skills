# Image-to-Video Guide

## Core Rule

Prompt only what the image cannot show. A still image already contains subject
identity, product form, wardrobe, palette, composition, and background.
Re-describing those static details often causes drift. Add motion, camera,
timing, transformation, lighting change, audio, and preservation constraints.

## Minimal Template

```
[Image1] is the reference; preserve [identity/product/scene] exactly.
Only [motion] changes. Camera: [one move].
Lighting: [source or transition]. Sound: [cue].
Constraint: [what must not change].
```

## Two I2V Modes

Decide the mode before writing.

### Hold Mode — the image IS the moment

Distribute three or four natural micro-actions across the clip:
- a blink, a breath, hair drift, a slow gaze shift
- Lock everything else with a double statement (positive + negative):
  `she stays seated by the window; she does not stand, turn, or leave frame`
- No camera move, or one slow push-in at most

### React Mode — something happens to the subject

Expand one emotion into sub-beats with real time to land:
- `she registers the sound, her eyes widen, color rises in her face
   over two to three seconds`
- Rushed emotions read as glitches; give the key beat at least two seconds
- If the image is clearly mid-scene rather than a natural opening frame,
  anchor the start explicitly

## Reference Role Assignment

| Role | Wording |
|---|---|
| Identity source | `[Image1] defines the character's face, build, and outfit` |
| Environment source | `[Image1] defines the location and lighting setup` |
| Product source | `[Image1] defines the product shape, label, and material` |
| Style source | `[Image1] defines the visual style and color palette` |

## Common I2V Mistakes

| Mistake | Why it fails | Fix |
|---|---|---|
| Re-describing the image content | Causes drift from the reference | Prompt only what changes |
| Too many simultaneous actions | Overwhelms the model | One primary action |
| No preservation constraint | Subject identity drifts | Add explicit lock statement |
| Camera move during lip-sync | Breaks mouth accuracy | Lock or slow push-in only |
