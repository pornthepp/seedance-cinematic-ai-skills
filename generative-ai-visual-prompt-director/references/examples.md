# Worked Examples

These examples show the same discipline across different platform families.
They are patterns, not universal command syntax.

## Example 1: Product Image Across Two Families

### Request

> Create a premium image of a reusable steel water bottle for an outdoor
> campaign. It should feel durable, not luxurious or fragile.

### Intent Spine

- Hero: brushed steel bottle with a few credible trail scuffs
- Action: standing securely on wet dark stone
- Composition: low three-quarter product view; label area readable and clear
- Light: cold overcast ambience plus a narrow warm dawn edge
- Materials: brushed steel, water beads, rough stone, distant mist
- Mood: capable, weather-tested, quiet confidence
- Exclude: floating object, spotless showroom surface, extra bottles

### Natural-Language Output

```text
Low three-quarter product photograph of one reusable brushed-steel water bottle
standing securely on wet dark stone at dawn. Fine trail scuffs and small water
beads make the bottle feel used but well cared for. Cold overcast ambience shapes
the steel while a narrow warm sunrise edge separates it from a soft misty ridge.
The clear label area faces camera. Grounded outdoor campaign mood, durable and
quietly capable. No extra bottles, floating object, or glossy showroom surface.
```

### Parameter-Driven Adaptation

```text
Prompt: [use the natural-language output above]
Controls:
  aspect ratio: wide campaign crop with safe copy space on the left
  variation strength: low to medium, preserving bottle geometry
  reproducibility: fixed for lighting comparisons
  reference influence: product identity only, if a product reference is supplied
```

Why it works: the visual intent remains readable without controls; each control
has a single production purpose.

## Example 2: Character Continuity In A Local Or Node Workflow

### Request

> Keep the same bicycle courier across three rainy-night images: arriving,
> checking an address, and leaving.

### Continuity Contract

```text
Immutable: woman in her late 20s, short black curls, small scar through right
eyebrow, mustard waterproof jacket, dark green messenger bag with silver buckle,
red bicycle with white front light.

Allowed change: body pose, facial effort, bicycle position, background traffic.

Scene anchors: rain-slick street, blue shop light from frame left, warm street
light from frame right, grounded documentary realism.
```

### Workflow Translation

1. Pin the model and graph versions.
2. Use one identity reference for face, hair, and silhouette.
3. Keep wardrobe and prop anchors in the positive conditioning for every image.
4. Use separate pose or composition conditioning for each beat.
5. Hold dimensions and reproducibility settings fixed during continuity tests.
6. Change only the action block:
   - arriving: brakes beside the curb, body leaning back
   - checking: one foot down, phone near chest, eyes scanning a doorway number
   - leaving: pushes from the curb, messenger bag pulling across her shoulder
7. Compare face, jacket, bag buckle, bicycle color, and light direction before
   refining atmosphere.

Why it works: identity and action are controlled by different stages, so a pose
change does not silently rewrite the character.

## Example 3: One Filmable Video Beat

### Request

> A child finds a tiny glowing seed in an abandoned greenhouse. Make it magical
> and cinematic.

### Video-Family Output

```text
Duration: 6 seconds
Opening state: Medium-wide view inside an abandoned greenhouse at blue hour. A
child kneels beside an overturned clay pot, still and cautious. Wet glass and
dead vines frame the space.

Action: The child brushes soil aside, discovers a seed giving off a soft green
glow, then slowly cups both hands around it. The glow brightens once and reveals
their astonished face.

Camera: One slow, steady push from medium-wide to medium close-up. No orbit or
angle change.

Environment motion: Fine rain tracks down the glass; one loose leaf trembles as
the light grows.

Performance: Curiosity becomes held-breath wonder through a pause, widened eyes,
and careful hands.

Continuity: Blue ambient light remains constant; green seed light affects only
nearby skin, soil, and glass. The seed stays between both palms.

Ending state: The child is still, centered with the glowing seed below their
face, ready for the next shot.
```

Why it works: one subject action, one camera move, and a defined ending state
turn “magical” into observable change without overloading the shot.
