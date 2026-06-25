---
name: seedance-cinematic-prompt-director
description: Use when creating, rewriting, or reviewing Seedance 2.0 video prompts for cinematic scenes, action scenes, realistic acting, camera movement, motion continuity, audio-video cues, original characters, anti-slop refinement, storyboard sequencing, technical format controls, or Thai-to-English film prompt direction.
---

# Seedance Cinematic Prompt Director

Turn a rough scene idea into a focused Seedance 2.0 prompt for a short, filmable video clip.

## Token Discipline

Start here. Read only the reference that matches the task:

| Need | Read |
|---|---|
| Multi-shot sequence, continuity, storyboard table | `references/storyboard-workflow.md` |
| Fight, chase, horror, romance, dialogue, product, music video modules | `references/scene-modules.md` |
| Duration, camera, technical controls, safety, IP, anti-slop, final templates | `references/technical-and-safety.md` |
| Full worked examples: action scene, multi-shot storyboard, fixing overloaded prompts | `references/examples.md` |
| Seedance 2.0 specific behaviors, duration, motion types, camera, artifacts | `references/model-quirks.md` |

## Working Assumptions

- Seedance prompts should describe original characters and filmable action.
- One clip usually covers one clear beat, often 4 to 15 seconds.
- If the user asks for a long scene, split it into shots.
- If the user gives image, audio, or video references, mention how each reference is used.
- Thai input can be transformed into polished English prompts while preserving intent.

## Quick Workflow

1. Read the dramatic intent.
2. Convert the idea into one visible beat.
3. Define character appearance and continuity anchors.
4. Choose camera behavior.
5. Add acting, motion, environment, light, and sound cues.
6. Remove vague style words and overloaded action.
7. Output the final prompt in clean English unless the user asks otherwise.

## Output Shape

```text
Duration:
Scene:
Character:
Action:
Performance:
Camera:
Lighting/Color:
Sound:
Continuity:
Final Seedance Prompt:
```

## Quality Gate

The prompt must be specific, original, physically clear, and possible to generate as a short clip. Avoid celebrity likenesses, copyrighted characters, vague "cinematic masterpiece" language, and too many actions in one shot.
