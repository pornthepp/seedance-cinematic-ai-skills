---
name: gpt-image-2-photoreal-synthesis
description: Use when creating, reviewing, or optimizing text prompts for OpenAI GPT Image 2, photoreal product images, portraits, editorial images, typography prompts, brand-consistent image prompts, visual realism, anti-slop prompt cleanup, or iterative prompt refinement.
---

# GPT Image 2 Photoreal Synthesis

Create precise text prompts for realistic, controlled, non-sloppy GPT Image 2 images.

## Token Discipline

Start here. Read only the reference that matches the task:

| Need | Read |
|---|---|
| Photoreal prompt structure for portrait, product, editorial, text, and brand images | `references/photoreal-prompt-framework.md` |
| Visual review, anatomy/text/material fixes, iterative prompt refinement | `references/visual-refinement-loop.md` |
| Full worked examples: product photo, editorial portrait, refinement loop | `references/examples.md` |
| GPT Image 2 specific behaviors, limitations, typography, multi-turn editing | `references/model-quirks.md` |

## Quick Workflow

1. Determine the image goal: product, portrait, editorial still, typography, brand image, or prompt cleanup.
2. Identify the subject, material, environment, lighting, camera feeling, color, and realism details.
3. Write the prompt as a production brief, not tag soup.
4. Use positive constraints: say exactly what should appear, where, and how.
5. Avoid Stable Diffusion and Midjourney-specific syntax unless the user explicitly switches pipelines.
6. If reviewing an image result, revise only the failing visual parts of the prompt.

## Prompt Skeleton

```text
[Subject and action]. [Material, texture, identity, or product details]. [Environment and context]. [Lighting]. [Camera, lens feeling, framing, and composition]. [Color, mood, realistic imperfections, and exact text if any].
```

## Output Shape

- Final prompt
- Risk notes
- Optional refinement pass

## Quality Gate

The prompt should be filmable, physically plausible, and specific. Do not promise unsupported controls. Do not rely on "secret tokens" or model folklore when an explicit visual instruction is clearer.
