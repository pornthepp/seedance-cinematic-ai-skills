# Visual Refinement Loop

Use this after an image exists, or when planning an iterative prompt refinement workflow.

## Four-Pass Review

### Pass 1: Composition And Geometry

Check:

- Horizon, perspective, vanishing lines.
- Object placement and scale.
- Crops and edge tangents.
- Repeated background patterns.
- Impossible reflections or shadows.

### Pass 2: Identity, Anatomy, And Materials

Check:

- Hands, fingers, joints, ears, teeth, and eyes.
- Product shape, labels, seams, edges, and surface behavior.
- Clothing layers and contact points.
- Skin texture versus plastic smoothing.
- Material-specific reflections and shadows.

### Pass 3: Text And Branding

Check:

- Exact spelling.
- Text placement.
- No duplicated or mutated letters.
- Brand marks only if the user has rights or provided references.
- Label perspective follows the surface.

### Pass 4: Lighting And Final Polish

Check:

- Key light direction matches shadows.
- Fill and contrast are plausible.
- Color cast is intentional.
- Over-sharpening, waxy skin, and plastic gloss are reduced.
- Grain or halation is subtle, not a filter pasted on top.

## Fix Patterns

### Hands

Prefer direct placement:

- `both hands in coat pockets`
- `right hand resting flat on the table`
- `hands clasped loosely behind the back`
- `crop below the elbows`

Avoid asking for "perfect hands" without a pose.

### Anatomy

State visible body mechanics:

- posture
- weight shift
- head angle
- shoulder position
- where each visible limb is placed

### Text

Keep text short. Quote exact words. Specify surface, position, orientation, and whether the text appears once.

### Product

State material and edge behavior:

- clear glass with real refraction
- brushed aluminum with fine linear grain
- matte paper label with slight texture
- realistic contact shadow under the object

## Refinement Output Format

```text
Observed issue:
Cause:
Prompt change:
Keep unchanged:
```

## Hard Rule

Refine the smallest failing part. Do not rewrite the whole prompt unless the concept itself is wrong.
