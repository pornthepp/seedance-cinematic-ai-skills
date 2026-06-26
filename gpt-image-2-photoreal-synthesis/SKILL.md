---
name: gpt-image-2-photoreal-synthesis
description:
  Use when creating, reviewing, or optimizing text prompts for OpenAI GPT Image
  2, photoreal product images, portraits, editorial images, typography prompts,
  brand-consistent image prompts, visual realism, anti-slop prompt cleanup, or
  iterative prompt refinement.
---

# GPT Image 2 Photoreal Synthesis

Create precise text prompts for realistic, controlled, non-sloppy GPT Image 2
images.

## Token Discipline

Start here. Read only the reference that matches the task:

| Need                                                                                | Read                                       |
| ----------------------------------------------------------------------------------- | ------------------------------------------ |
| Photoreal prompt structure for portrait, product, editorial, text, and brand images | `references/photoreal-prompt-framework.md` |
| Visual review, anatomy/text/material fixes, iterative prompt refinement             | `references/visual-refinement-loop.md`     |
| Full worked examples: product photo, editorial portrait, refinement loop            | `references/examples.md`                   |
| GPT Image 2 specific behaviors, limitations, typography, multi-turn editing         | `references/model-quirks.md`               |
| Camera angles, shot size, composition rules, lens physics, camera height            | `../cinematic-camera-composition-director/references/shot-composition-guide.md` |
| Advanced camera composition, blocking, layout, multi-layered depth                  | `../cinematic-camera-composition-director/references/advanced-techniques.md` |
| Color look development, palettes, colorist grading layers, zone shading             | `../cinematic-color-look-development/references/advanced-techniques.md` |
| Physical character behavior, posture, joint/limb contact points, expressions        | `../modern-acting-performance-mastery/references/performance-direction-guide.md` |
| Cultural, historical, or gender-safe character representation guidelines           | `../ethical-character-representation/references/representation-review-guide.md` |

## Quick Workflow

1. Determine the image goal: product, portrait, editorial still, typography,
   brand image, or prompt cleanup.
2. Identify the subject, material, environment, lighting, camera feeling, color,
   and realism details. **Consult sibling cinematic skills (composition, color look development, acting performance, ethical representation) to ensure professional cinematic control.**
3. Write the prompt as a production brief, not tag soup.
4. Use positive constraints: say exactly what should appear, where, and how.
5. Avoid Stable Diffusion and Midjourney-specific syntax unless the user
   explicitly switches pipelines.
6. If reviewing an image result, revise only the failing visual parts of the
   prompt.

## Prompt Skeleton

```text
[Subject and action]. [Material, texture, identity, or product details]. [Environment and context]. [Lighting]. [Camera, lens feeling, framing, and composition]. [Color, mood, realistic imperfections, and exact text if any].
```

## Output Shape

- Final prompt
- Risk notes
- Optional refinement pass

## Quality Gate

The prompt should be filmable, physically plausible, and specific. Do not
promise unsupported controls. Do not rely on "secret tokens" or model folklore
when an explicit visual instruction is clearer.
