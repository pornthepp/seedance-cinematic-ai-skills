---
name: seedance-cinematic-prompt-director
description: Use when creating, rewriting, or reviewing Seedance 2.0 video prompts for cinematic scenes, action scenes, realistic acting, camera movement, motion continuity, audio-video cues, original characters, anti-slop refinement, storyboard sequencing, technical format controls, or Thai-to-English film prompt direction.
license: Complete terms in LICENSE.txt
---

# Seedance Cinematic Prompt Director

Direct the scene — don't decorate it. Every word in a Seedance prompt must
describe something the model can generate: a visible action, a camera position,
a light source, a sound. If the model can't draw it, cut it.

## Token Discipline

Start here. Read only the reference that matches the task:

| Need                                                                                           | Read                                  |
| ---------------------------------------------------------------------------------------------- | ------------------------------------- |
| Multi-shot sequence, continuity, storyboard table                                              | `references/storyboard-workflow.md`   |
| Fight, chase, horror, romance, dialogue, product, music video, commercial, educational modules | `references/scene-modules.md`         |
| Duration, camera, technical controls, safety, IP, anti-slop reference table, final templates   | `references/technical-and-safety.md`  |
| Full worked examples: action scene, multi-shot storyboard, fixing overloaded prompts           | `references/examples.md`              |
| Seedance 2.0 specific behaviors, duration, motion types, camera, artifacts                     | `references/model-quirks.md`          |
| Hollow words → observable replacements, the six slop classes                                   | `references/anti-slop-lexicon.md`     |
| Multi-shot cuts inside one generation (Shot 1: / Shot 2: / Shot 3:), shot budgets              | `references/multishot-grammar.md`     |
| Image-to-Video: Hold mode vs React mode, I2V prompt template                                   | `references/i2v-guide.md`             |
| Dialogue, lip-sync, beat-sync, audio reference mapping, five sound layers                      | `references/audio-guide.md`           |
| Why rules work: attention budget, no-NOT, trajectory prior, error compounding                  | `references/model-mechanics.md`       |
| Result came back wrong: five verdicts, one-variable rule, attempt budget                       | `references/retake-protocol.md`       |
| Strengths to exploit, limits to design around                                                  | `references/capability-map.md`        |
| Output failed: symptom → cause → repair table                                                  | `references/failure-atlas.md`         |
| Content filter triggers: safe rewording table, false-positive fixes                            | `references/filter-vocab.md`          |
| How much story fits one generation: beat buckets, scope firewall                               | `references/event-density.md`         |

## Working Assumptions

- Every descriptor must map to something visible, audible, or physically
  executable. If the model cannot render it as pixels or audio, it does not
  belong in the prompt.
- Seedance prompts describe original characters and filmable action — no
  celebrities, no copyrighted characters.
- One clip covers one clear beat, usually 4 to 15 seconds.
- If the user asks for a long scene, split it into shots.
- If the user gives image, audio, or video references, mention how each
  reference is used.
- Thai input is transformed into precise English while preserving creative
  intent.

## Quick Workflow

0. Choose mode — T2V (text-to-video), I2V (image-to-video), V2V
   (video-to-video), or FLF2V (first/last frame). If I2V, read
   `references/i2v-guide.md`. If multi-shot, read
   `references/multishot-grammar.md`.
1. Read the dramatic intent — identify the single visible beat.
2. Define character using only drawable details: face, build, clothing, posture.
   Not personality, not backstory.
3. Describe action as physical mechanics — who moves where, what force, what
   result. Not "fights dramatically."
4. Choose camera: name the shot size, angle, and movement. Not "cinematic
   angle."
5. Add performance as visible behavior — breath, gaze direction, posture shift,
   hesitation. Not "emotional."
6. Set lighting by source and direction. Set sound by specific source. Not
   "dramatic lighting" or "ambient music."
7. Review: for every word, ask "Can the model draw this?" Replace or cut
   anything that fails.
8. Output the final prompt in clean English unless the user asks otherwise.

## Output Shape

Read `templates/scene-prompt.md` first. Fill in each field:

- `Duration` — clip length in seconds
- `Scene` — location, time, weather as physical description
- `Character` — face, build, clothing, posture; what the camera sees
- `Action` — physical mechanics: who moves where, what happens
- `Performance` — visible behavior: breath, gaze, posture, hesitation
- `Camera` — shot size, angle, movement; name the behavior
- `Lighting/Color` — source, direction, color temperature; not adjectives
- `Sound` — specific sources: footsteps, wind, breath, silence
- `Continuity` — how this shot connects to the previous and next
- `Final Seedance Prompt` — the assembled output in clean English

## Quality Gate

Every word must pass one test: **can the model draw this?**

- One action beat per clip.
- Character is original and described in visual terms only.
- Camera behavior is named, not implied.
- Lighting is described by source and direction, not by mood.
- Sound is a specific source, not a vague label.
- No decoration survives: no "cinematic," "dramatic," "beautiful," "epic,"
  "stunning," "masterful." (See `references/anti-slop-lexicon.md`)
- If a word cannot be rendered as pixels or audio, it is cut.
- Multi-shot prompts use `Shot N:` labels and budget ~4–6s per shot.
- Audio intent is explicit: dialogue, ambience, SFX, music, or silence.
- If the result is wrong, triage before re-rolling blindly.
  (See `references/retake-protocol.md`)
