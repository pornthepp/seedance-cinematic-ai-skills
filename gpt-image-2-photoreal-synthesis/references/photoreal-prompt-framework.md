# Photoreal Prompt Framework

Use this when building the final image prompt.

## Six-Part Blueprint

Write a complete production brief:

1. Subject and action.
2. Material, surface, body, product, or identity details.
3. Environment and context.
4. Lighting setup.
5. Camera, lens feeling, angle, framing, and composition.
6. Color, mood, realistic imperfections, and exact text.

## Prompt Rules

- Put the most important requirement first.
- Use complete sentences, not tag soup.
- Keep one main visual idea per image.
- Limit adjectives; prefer concrete nouns and visible details.
- Name spatial placement when layout matters.
- For exact text, quote it and state where it appears.
- Request strict adherence in plain language when the prompt must stay
  controlled.

## Strict Adherence Clause

Use a plain control sentence when the output must stay disciplined:

```text
Follow these visual requirements exactly. Do not add extra characters, props, logos, fantasy styling, or decorative elements not listed.
```

## Photoreal Details That Help

- Natural skin texture, visible pores, fine hair, slight asymmetry.
- Real material behavior: glass reflections, brushed metal grain, fabric weave,
  dust, fingerprints, micro-scratches.
- Plausible lighting: key light direction, fill level, shadow softness, rim
  light, practical light source.
- Lens behavior: natural perspective, shallow or deep depth of field, macro
  product detail, controlled edge sharpness.
- Imperfections: mild film grain, subtle halation, stray hairs, imperfect folds,
  real-world surface wear.

## Useful Setups

### Portrait

```text
Photoreal portrait of [person], [visible action or expression]. Natural skin texture, slight asymmetry, realistic hair detail. Large soft key light at 45 degrees with gentle fill. 85mm portrait lens feeling, shallow depth of field, sharp eyes, soft background falloff.
```

### Product

```text
Photoreal studio product image of [product], showing [specific materials and label text]. Clean surface, controlled reflections, crisp product edges, realistic contact shadow. Macro lens feeling, f/8 depth, large softbox reflection, neutral background.
```

### Editorial Or Cinematic Still

```text
Photoreal editorial image of [subject] in [place], during [time or weather]. The composition emphasizes [story idea]. Natural practical lighting, controlled contrast, 35mm lens feeling, layered foreground and background, restrained color palette.
```

### Text Or Typography

```text
Create a photoreal image with the exact text "[TEXT]" printed on [surface]. The text is centered, correctly spelled, flat on the surface, readable, and not duplicated anywhere else.
```

## Avoid

- Long negative prompt lists from Stable Diffusion syntax.
- Weighted negative syntax from Stable Diffusion unless the user's tool
  explicitly supports it.
- Midjourney command flags for aspect ratio, style, chaos, seed, or stylization
  when the target is GPT Image 2.
- "Secret metadata token" tricks as the main control method.
- Camera model names with no visual purpose.
- Overloaded prompts with several unrelated actions.
