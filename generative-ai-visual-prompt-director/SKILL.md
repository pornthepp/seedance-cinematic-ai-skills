---
name: generative-ai-visual-prompt-director
description: Use when turning a complete visual brief into a platform-neutral AI image or video prompt, adapting one concept across platform families, or diagnosing and refining a generated result. Do not use for camera-only, color-only, acting-only, sound-only, or narrative-only requests; route those to the specialist skills.
license: Complete terms in ../LICENSE.txt
---

# Generative AI Visual Prompt Director

Turn a visual brief into a concrete production direction. Default to durable visual language; add platform-specific controls only when the user requests a known target and the controls are verified.

## Token Routing

Read only what the task needs:

| Need | Read |
| --- | --- |
| Build the prompt from first principles | [visual-prompt-framework.md](references/visual-prompt-framework.md) |
| Choose precise visual terms | [visual-language.md](references/visual-language.md) |
| Adapt to a platform family | [platform-adaptation.md](references/platform-adaptation.md) |
| Diagnose a weak result | [iteration-and-troubleshooting.md](references/iteration-and-troubleshooting.md) |
| See complete image/video examples | [examples.md](references/examples.md) |

Route specialist-only requests instead of duplicating them: [camera and composition](../cinematic-camera-composition-director/SKILL.md), [color and look](../cinematic-color-look-development/SKILL.md), [acting and performance](../modern-acting-performance-mastery/SKILL.md), [ethical representation](../ethical-character-representation/SKILL.md), [narrative analysis](../short-film-artistic-narrative-analysis/SKILL.md), or [soundscape](../cinematic-music-soundscape-design/SKILL.md). Use a platform-specific sibling only when the user names that target: [GPT Image 2](../gpt-image-2-photoreal-synthesis/SKILL.md) or [Seedance video](../seedance-cinematic-prompt-director/SKILL.md).

## Workflow

1. Identify output mode: still image, single video shot, sequence, or prompt review.
2. Extract intent, subject/action, environment, composition, lighting, color, material, mood, references, and hard constraints. Ask only when missing information would materially change the result; otherwise state assumptions.
3. Resolve conflicts. Apply the Ref-over-Text rule: ensure the text prompt does not contradict or redundantly repeat details already present in active reference images. Prioritize identity and required content before style detail.
4. For video, add initial state, motion, camera behavior, timing, continuity, and end state. For images, emphasize spatial arrangement and the decisive moment.
5. Write one coherent master prompt using observable visual instructions, not tag soup or vague praise words.
6. Add exclusions as concise risk controls. Adapt syntax only for a verified target.
7. When refining, change one failing variable at a time and preserve successful elements.

## Output Shape

Follow the user's requested format. For an unrestricted request, read [visual-prompt-brief.md](templates/visual-prompt-brief.md) and return:

- `Assumptions`
- `Master prompt`
- `Exclusions / risk controls`
- `Platform adaptation notes`
- `Controlled variants` (2-3 only when useful; label the single changed variable)
- `Next refinement test`

For prompt-only, JSON, table, or other constrained output, include only the fields that fit that format. Do not add commentary the user excluded.

## Quality Gate

Before finalizing, verify that the prompt is concrete, internally consistent, physically and temporally plausible, respects the Ref-over-Text rule (avoiding text conflicts with active references), and is appropriate to image or video. Reference roles must be explicit: content, composition, style attributes, or identity. Do not promise unsupported controls, present guesses as facts, or imitate a living artist by name when visual attributes can express the intent.
