# GPT Image 2 Model-Specific Quirks

Knowledge specific to GPT Image 2 that goes beyond general prompt writing. This
file covers behaviors, limitations, and techniques that only apply to this
model.

## How GPT Image 2 Differs From Other Image Models

GPT Image 2 is not a diffusion model. It is an autoregressive transformer that
generates images natively within the GPT architecture. This changes how
prompting works:

- **Natural language over tag syntax.** The model reads prompts as prose, not as
  comma-separated tags. Complete sentences with spatial relationships outperform
  keyword lists. "A red cup on the left side of a wooden table" works better
  than "red cup, wooden table, left composition."
- **No negative prompts.** Unlike Stable Diffusion, there is no `--no` or
  negative prompt field. To exclude something, use positive constraints: "only
  one person in the frame" instead of trying to negate crowds.
- **No CFG scale, steps, or sampler.** These diffusion-specific controls do not
  exist. The model's internal reasoning handles generation quality.
- **No LoRA, embeddings, or custom checkpoints.** Style control comes entirely
  through prompt description, not through model modifications.

## Internal Reasoning (Thinking)

GPT Image 2 uses internal reasoning before generating. The model interprets the
prompt, plans composition, and makes visual decisions before pixel generation
begins. This means:

- **Longer, more specific prompts generally produce better results** because the
  model has more information to reason about. Unlike diffusion models where very
  long prompts can degrade, GPT Image 2 benefits from detail.
- **Contradictory instructions confuse the reasoning.** If the prompt says
  "close-up" but then describes a full landscape, the model must resolve the
  conflict. Be internally consistent.
- **Implicit knowledge is used.** The model understands that "a café in Paris"
  implies certain architectural details, light quality, and atmosphere. You can
  rely on this knowledge while adding specific overrides where you want control.

## Typography and Text Rendering

Text rendering is a headline feature of GPT Image 2 but has specific reliability
patterns:

### What Works Well

- Short text (1-5 words) on flat, front-facing surfaces.
- Text in quotes with explicit placement:
  `The word "OPEN" printed in red on a white sign above the door.`
- Single text element per image.
- Latin alphabet text in standard fonts.
- Text on signs, labels, book covers, and product packaging.

### What Requires Care

- Multiple separate text elements in one image. Reliability drops with each
  additional text block. If you need 3+ text elements, prioritize the most
  important one with explicit instructions and accept variation in others.
- Curved text on cylindrical surfaces (bottles, cans). Specify "the label wraps
  around the cylinder" and accept slight perspective variation.
- Small text below ~12pt equivalent. The model may simplify or blur small text.
- Non-Latin scripts (Thai, Arabic, Chinese, Japanese, Korean). The model can
  render these but with lower reliability for correct character formation. For
  critical text in these scripts, verify carefully and expect refinement rounds.
- Handwritten or calligraphic styles. Specify "printed" or "typed" if you need
  clean text; "handwritten" introduces intentional variation that may affect
  legibility.

### What Fails Often

- Very long text (full sentences or paragraphs) rendered as readable text in an
  image.
- Text that must be pixel-perfect at small sizes.
- Multiple fonts in one text element.
- Text on heavily textured or patterned backgrounds where the model cannot
  separate text from texture.

### Typography Technique

```text
The exact text "[YOUR TEXT]" appears once, printed in [color] [font style] on [surface].
The text is [position], correctly spelled, flat on the surface, and not duplicated
anywhere else in the image.
```

The phrase "not duplicated anywhere else" is important — without it, the model
sometimes echoes text on reflections, shadows, or background elements.

## Multi-Turn Editing

GPT Image 2 supports iterative refinement through conversation. When you
generate an image and then ask for changes:

### How Multi-Turn Works

- The model can modify an existing generated image based on follow-up
  instructions.
- It retains context from the original prompt and the generated result.
- Targeted edits ("make the sky warmer," "remove the object on the left") work
  better than full regeneration.

### Effective Multi-Turn Patterns

- **Isolate the change.** "Keep everything the same. Change only the lighting
  from overhead to 45-degree side lighting." The more specific the isolation,
  the more the model preserves.
- **Reference the original.** "In the image you just generated, the hand
  position is awkward. Move the right hand to rest on the table instead."
- **Incremental refinement.** Fix one problem per turn. Stacking multiple fixes
  in one turn reduces reliability.

### Multi-Turn Limitations

- The model may drift from the original after 3-4 edit rounds. Details in
  non-edited areas may shift subtly.
- Major composition changes (moving the subject from left to right) effectively
  require regeneration, not editing.
- Style consistency across many edits can degrade. If the image needs many
  changes, it is often better to write a single improved prompt and regenerate.

## Output Formats and Sizes

- **Square (1024×1024):** Default. Best for portraits, product shots, and
  compositions with a central subject.
- **Landscape (1536×1024, 1792×1024):** Better for environmental shots, wide
  compositions, and scenes with horizontal movement.
- **Portrait (1024×1536, 1024×1792):** Better for full-body figures, vertical
  architecture, and tall compositions.
- **Aspect ratio affects composition.** The model adapts framing to the aspect
  ratio. A wide landscape ratio naturally produces more environmental context; a
  tall portrait ratio emphasizes vertical elements. Choose the ratio that
  matches your composition intent, not just your delivery format.

## Known Artifacts and Workarounds

| Artifact                       | When It Happens                                   | Workaround                                                                                                                                   |
| ------------------------------ | ------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Extra fingers or fused fingers | Hands in complex poses, gripping small objects    | Specify hand position explicitly: "right hand flat on table," "hands in coat pockets," "hands clasped behind back." Simplify the hand state. |
| Duplicate objects              | Prompt does not specify quantity                  | Add "one [object] only" or "a single [object]" when quantity matters.                                                                        |
| Text duplication               | Text appears in reflections or background         | Add "the text appears once only and is not reflected or repeated elsewhere."                                                                 |
| Plastic skin texture           | Portraits with heavy beauty/fashion language      | Add "natural skin texture with visible pores, fine hair, slight asymmetry." Explicitly request imperfections.                                |
| Impossible shadows             | Complex multi-source lighting described vaguely   | Specify one key light direction and describe shadow behavior: "shadow falls to the lower right."                                             |
| Over-saturation                | Mood words like "vibrant," "stunning," "dramatic" | Replace with specific color values or references: "muted earth tones" or "desaturated cool palette with one warm accent."                    |
| Symmetry bias                  | Centered compositions, product shots              | If asymmetry is wanted, explicitly break it: "the subject sits at the right third of the frame."                                             |

## What GPT Image 2 Does Better Than Diffusion Models

- **Spatial reasoning.** "Put A to the left of B, with C behind both" is more
  reliably executed than in Stable Diffusion or Midjourney.
- **Text rendering.** Far more reliable than any diffusion model for short text.
- **Prompt coherence.** Long, detailed prompts maintain coherence better.
  Diffusion models tend to lose detail focus as prompts grow.
- **Consistent style from prose.** Describing a photographic style in natural
  language ("shot on medium format film with shallow depth of field and slight
  warm color cast") produces more consistent results than tag-based style
  matching.
- **Object counting.** "Three apples on a plate" more reliably produces exactly
  three apples.

## What GPT Image 2 Does Worse Than Diffusion Models

- **Speed.** Generation is slower than optimized diffusion pipelines.
- **Fine style control.** Without LoRA or embeddings, matching a very specific
  aesthetic (a particular photographer's style, a specific film stock look)
  requires more prompt engineering effort.
- **Reproducibility.** No seed parameter for exact reproduction. Similar prompts
  produce similar but not identical results.
- **Batch variation.** You cannot generate 4 variations simultaneously and pick
  the best one in the same way as Midjourney's grid.

## Prompt Anti-Patterns Specific to GPT Image 2

| Anti-Pattern                                                    | Why It Fails                                              | Replace With                                                                                                              |
| --------------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `--ar 16:9 --v 6 --style raw`                                   | Midjourney syntax, ignored or misinterpreted              | Request landscape aspect ratio in the API call; describe style in prose                                                   |
| `(masterpiece:1.4), (best quality:1.2)`                         | Stable Diffusion weighted token syntax, not supported     | Remove entirely — quality is not controlled by weight tags                                                                |
| `negative prompt: ugly, deformed, blurry`                       | No negative prompt field exists                           | Use positive constraints: "clean composition, anatomically correct, sharp focus"                                          |
| `Steps: 30, CFG: 7, Sampler: DPM++`                             | Diffusion generation parameters, not applicable           | Remove entirely                                                                                                           |
| `<lora:detail_enhancer:0.8>`                                    | LoRA not supported                                        | Describe the desired detail level in prose                                                                                |
| Camera model names as quality tokens (`shot on Hasselblad X2D`) | The model does not simulate specific camera sensor output | Describe the visual qualities you want: "medium format film feeling with shallow depth, fine grain, and rich color depth" |
