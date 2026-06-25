# Skill Loading Index

Use this index before opening any skill. Goal: choose the narrowest useful skill and avoid loading unrelated guidance.

## Preflight Gate

Open `PREFLIGHT_ROUTER.md` only when the request is vague, broad, multi-domain, or likely to load more than one skill. If the user task is already precise, skip preflight and route directly.

## Routing Table

| Need | Open This Skill | Read References When |
|---|---|---|
| Shot plan, image prompt, camera angle, lens, framing, continuity | `cinematic-camera-composition-director/SKILL.md` | The user asks for exact shot language, storyboard format, or composition options |
| GPT Image 2 text prompt, photoreal prompt writing, prompt cleanup, visual QA | `gpt-image-2-photoreal-synthesis/SKILL.md` | The task needs prompt structure, realism detail, typography prompt control, or anti-slop refinement |
| Palette, look, LUT, grade, visual mood, color continuity | `cinematic-color-look-development/SKILL.md` | The answer needs palette logic, lighting notes, or DI/colorist detail |
| Score, ambience, sound cue, silence, sonic identity | `cinematic-music-soundscape-design/SKILL.md` | The task needs cue sheets, motif planning, or sound palette choices |
| Short film script, pitch, festival critique, narrative structure | `short-film-artistic-narrative-analysis/SKILL.md` | The user needs a full artistic review or rewrite plan |
| Seedance 2.0 video prompt, short clip, action, storyboard sequence | `seedance-cinematic-prompt-director/SKILL.md` | The task needs scene modules, technical controls, or multi-shot continuity |
| Acting choice, emotional beat, line delivery, actor coaching | `modern-acting-performance-mastery/SKILL.md` | The task needs a specific acting method, body/voice work, or rehearsal direction |
| Character representation, culture, identity, bias, accessibility, cast/world patterns | `ethical-character-representation/SKILL.md` | The task needs a structured representation audit |

## Reference Depth

Each skill has layered references. Load only what the task needs:

| Reference Type | File Pattern | Load When |
|---|---|---|
| Core guide | `references/*-guide.md`, `references/*-framework.md`, `references/*-index.md` | The task needs vocabulary, structured output, or a review table |
| Worked examples | `references/examples.md` | The user wants to see a full input → output demonstration, or the agent needs a pattern to follow |
| Model quirks | `references/model-quirks.md` | The task targets GPT Image 2 or Seedance 2.0 and needs to avoid model-specific pitfalls |
| Advanced techniques | `references/advanced-techniques.md` | The task requires professional-level depth beyond the core workflow |

## Category Map

### Image and Shot Craft

- `cinematic-camera-composition-director`
- `gpt-image-2-photoreal-synthesis`
- `cinematic-color-look-development`

### Video Prompt Craft

- `seedance-cinematic-prompt-director`
- Optional support: `cinematic-camera-composition-director`, `modern-acting-performance-mastery`, `cinematic-color-look-development`

### Film Story and Performance

- `short-film-artistic-narrative-analysis`
- `modern-acting-performance-mastery`
- `cinematic-music-soundscape-design`

### Ethics and Character Systems

- `ethical-character-representation`

## Routing Examples

| User Request | Load |
|---|---|
| "Write a GPT Image 2 product photo prompt" | `gpt-image-2-photoreal-synthesis/SKILL.md` |
| "Make this OpenAI image prompt more realistic" | `gpt-image-2-photoreal-synthesis/SKILL.md` |
| "Why does GPT Image 2 keep duplicating my text?" | `gpt-image-2-photoreal-synthesis/SKILL.md` → `references/model-quirks.md` |
| "Improve the camera angle for this scene" | `cinematic-camera-composition-director/SKILL.md` |
| "Show me an example of a good shot sequence" | `cinematic-camera-composition-director/SKILL.md` → `references/examples.md` |
| "Create a Seedance 2.0 fight prompt" | `seedance-cinematic-prompt-director/SKILL.md` |
| "What duration works best for Seedance?" | `seedance-cinematic-prompt-director/SKILL.md` → `references/model-quirks.md` |
| "Give this character better acting beats" | `modern-acting-performance-mastery/SKILL.md` |
| "Build a color palette for this short film" | `cinematic-color-look-development/SKILL.md` |
| "What's wrong with my teal and orange grade?" | `cinematic-color-look-development/SKILL.md` → `references/advanced-techniques.md` |
| "Review the sound design of this scene" | `cinematic-music-soundscape-design/SKILL.md` |
| "Audit this character for stereotypes" | `ethical-character-representation/SKILL.md` |
| "Score my cast on the representation rubric" | `ethical-character-representation/SKILL.md` → `references/representation-review-guide.md` |
| "Make it cinematic." | `PREFLIGHT_ROUTER.md`, then ask one focus question |

## Token Budget Rules

- One narrow task: load 1 `SKILL.md`.
- Cross-domain task: load the lead skill, then at most 1 support skill at a time.
- Deep task: read only the specific `references/*.md` named by the lead skill.
- Examples and advanced techniques: load only when the user asks for demonstrations or the task needs professional-level depth.
- Model quirks: load only when the task targets a specific model (GPT Image 2 or Seedance 2.0).
- Run preflight only when it prevents loading the wrong skill or too many skills.
- Do not load every skill just because the task is cinematic.
