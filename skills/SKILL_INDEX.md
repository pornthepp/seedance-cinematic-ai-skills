# Skill Loading Index

Use this index before opening any skill. Goal: choose the narrowest useful skill
and avoid loading unrelated guidance.

## Preflight Gate

Open `PREFLIGHT_ROUTER.md` only when the request is vague, broad, multi-domain,
or likely to load more than one skill. If the user task is already precise, skip
preflight and route directly.

## Routing Table

| Need                                                                                  | Open This Skill                                   | Read References When                                                                                |
| ------------------------------------------------------------------------------------- | ------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Shot plan, image prompt, camera angle, lens, framing, continuity                      | `cinematic-camera-composition-director/GUIDE.md`  | The user asks for exact shot language, storyboard format, or composition options                    |
| GPT Image 2 text prompt, photoreal prompt writing, prompt cleanup, visual QA          | `gpt-image-2-photoreal-synthesis/GUIDE.md`        | The task needs prompt structure, realism detail, typography prompt control, or anti-slop refinement |
| Palette, look, LUT, grade, visual mood, color continuity                              | `cinematic-color-look-development/GUIDE.md`       | The answer needs palette logic, lighting notes, or DI/colorist detail                               |
| Score, ambience, sound cue, silence, sonic identity                                   | `cinematic-music-soundscape-design/GUIDE.md`      | The task needs cue sheets, motif planning, or sound palette choices                                 |
| Short film script, pitch, festival critique, narrative structure                      | `short-film-artistic-narrative-analysis/GUIDE.md` | The user needs a full artistic review or rewrite plan                                               |
| Seedance 2.0 video prompt, short clip, action, storyboard sequence                    | `seedance-cinematic-prompt-director/GUIDE.md`     | The task needs scene modules, technical controls, or multi-shot continuity                          |
| Seedance I2V (image-to-video), animating a still, hold/react modes                   | `seedance-cinematic-prompt-director/GUIDE.md`     | Load `references/i2v-guide.md` for I2V-specific workflow                                            |
| Seedance multi-shot, 2–3 cuts in one generation, Shot 1:/2:/3:                        | `seedance-cinematic-prompt-director/GUIDE.md`     | Load `references/multishot-grammar.md` for multi-shot grammar                                       |
| Seedance audio, dialogue, lip-sync, beat-sync, sound design                           | `seedance-cinematic-prompt-director/GUIDE.md`     | Load `references/audio-guide.md` for audio-specific workflow                                        |
| Seedance result is wrong, troubleshoot, fix failed generation                         | `seedance-cinematic-prompt-director/GUIDE.md`     | Load `references/retake-protocol.md` + `references/failure-atlas.md`                                |
| Acting choice, emotional beat, line delivery, actor coaching                          | `modern-acting-performance-mastery/GUIDE.md`      | The task needs a specific acting method, body/voice work, or rehearsal direction                    |
| Character representation, culture, identity, bias, accessibility, cast/world patterns | `ethical-character-representation/GUIDE.md`       | The task needs a structured representation audit                                                    |
| Genre-specific approach: product ad, action, horror, anime, documentary, music video  | `short-film-artistic-narrative-analysis/GUIDE.md` | Load `references/genre-guides.md` for genre-specific priorities                                     |

## Reference Depth

Each skill has layered references. Load only what the task needs:

| Reference Type       | File Pattern                                                                  | Load When                                                                                         |
| -------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Output template      | `templates/*.md`                                                              | The skill's Output Shape section directs you to read it first; always load before filling output  |
| Core guide           | `references/*-guide.md`, `references/*-framework.md`, `references/*-index.md` | The task needs vocabulary, structured output, or a review table                                   |
| Worked examples      | `references/examples.md`                                                      | The user wants to see a full input → output demonstration, or the agent needs a pattern to follow |
| Model quirks         | `references/model-quirks.md`                                                  | The task targets GPT Image 2 or Seedance 2.0 and needs to avoid model-specific pitfalls           |
| Advanced techniques  | `references/advanced-techniques.md`                                           | The task requires professional-level depth beyond the core workflow                               |
| Anti-slop lexicon    | `references/anti-slop-lexicon.md`                                             | The prompt has vague quality words that need replacing with observable details                     |
| Multi-shot grammar   | `references/multishot-grammar.md`                                             | The user wants 2–3 shots with cuts in a single generation                                         |
| I2V guide            | `references/i2v-guide.md`                                                     | The user provides a still image and wants to animate it                                           |
| Audio guide          | `references/audio-guide.md`                                                   | The task involves dialogue, lip-sync, beat-sync, or sound design                                  |
| Model mechanics      | `references/model-mechanics.md`                                               | Understanding WHY a rule works helps derive guidance for uncovered cases                           |
| Retake protocol      | `references/retake-protocol.md`                                               | The user's generation came back wrong and needs systematic diagnosis                               |
| Capability map       | `references/capability-map.md`                                                | Planning phase: know what to exploit and what to avoid                                             |
| Failure atlas        | `references/failure-atlas.md`                                                 | The output has a specific visual/motion failure to diagnose                                        |
| Filter vocabulary    | `references/filter-vocab.md`                                                  | The prompt triggers content filters or needs safe professional rewording                           |
| Event density        | `references/event-density.md`                                                 | Deciding how much story fits in one clip vs splitting into a sequence                              |
| Genre guides         | `references/genre-guides.md`                                                  | The user specifies a genre and needs genre-appropriate priorities                                  |

## Category Map

### Image and Shot Craft

- `cinematic-camera-composition-director`
- `gpt-image-2-photoreal-synthesis`
- `cinematic-color-look-development`

### Video Prompt Craft

- `seedance-cinematic-prompt-director`
- Optional support: `cinematic-camera-composition-director`,
  `modern-acting-performance-mastery`, `cinematic-color-look-development`

### Film Story and Performance

- `short-film-artistic-narrative-analysis`
- `modern-acting-performance-mastery`
- `cinematic-music-soundscape-design`

### Ethics and Character Systems

- `ethical-character-representation`

## Routing Examples

| User Request                                     | Load                                                                                      |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| "Write a GPT Image 2 product photo prompt"       | `gpt-image-2-photoreal-synthesis/GUIDE.md`                                                |
| "Make this OpenAI image prompt more realistic"   | `gpt-image-2-photoreal-synthesis/GUIDE.md`                                                |
| "Why does GPT Image 2 keep duplicating my text?" | `gpt-image-2-photoreal-synthesis/GUIDE.md` → `references/model-quirks.md`                 |
| "Improve the camera angle for this scene"        | `cinematic-camera-composition-director/GUIDE.md`                                          |
| "Show me an example of a good shot sequence"     | `cinematic-camera-composition-director/GUIDE.md` → `references/examples.md`               |
| "Create a Seedance 2.0 fight prompt"             | `seedance-cinematic-prompt-director/GUIDE.md`                                             |
| "What duration works best for Seedance?"         | `seedance-cinematic-prompt-director/GUIDE.md` → `references/model-quirks.md`              |
| "Give this character better acting beats"        | `modern-acting-performance-mastery/GUIDE.md`                                              |
| "Build a color palette for this short film"      | `cinematic-color-look-development/GUIDE.md`                                               |
| "What's wrong with my teal and orange grade?"    | `cinematic-color-look-development/GUIDE.md` → `references/advanced-techniques.md`         |
| "Review the sound design of this scene"          | `cinematic-music-soundscape-design/GUIDE.md`                                              |
| "Audit this character for stereotypes"           | `ethical-character-representation/GUIDE.md`                                               |
| "Score my cast on the representation rubric"     | `ethical-character-representation/GUIDE.md` → `references/representation-review-guide.md` |
| "Make it cinematic."                             | `PREFLIGHT_ROUTER.md`, then ask one focus question                                        |
| "Animate this still image with Seedance"         | `seedance-cinematic-prompt-director/GUIDE.md` → `references/i2v-guide.md`                 |
| "Create a 3-shot sequence in one clip"           | `seedance-cinematic-prompt-director/GUIDE.md` → `references/multishot-grammar.md`         |
| "Add dialogue and lip-sync to this scene"        | `seedance-cinematic-prompt-director/GUIDE.md` → `references/audio-guide.md`               |
| "My Seedance output looks wrong, help fix it"    | `seedance-cinematic-prompt-director/GUIDE.md` → `references/retake-protocol.md` + `failure-atlas.md` |
| "Remove slop words from this prompt"             | `seedance-cinematic-prompt-director/GUIDE.md` → `references/anti-slop-lexicon.md`         |
| "What can Seedance 2.0 actually do well?"        | `seedance-cinematic-prompt-director/GUIDE.md` → `references/capability-map.md`            |
| "My prompt keeps getting blocked by the filter"  | `seedance-cinematic-prompt-director/GUIDE.md` → `references/filter-vocab.md`              |
| "Write a horror scene prompt"                    | `seedance-cinematic-prompt-director/GUIDE.md` + `short-film.../references/genre-guides.md`|

## Token Budget Rules

- One narrow task: load 1 `GUIDE.md`.
- Cross-domain task: load the lead skill, then at most 1 support skill at a
  time.
- Deep task: read only the specific `references/*.md` named by the lead skill.
- Examples and advanced techniques: load only when the user asks for
  demonstrations or the task needs professional-level depth.
- Model quirks: load only when the task targets a specific model (GPT Image 2 or
  Seedance 2.0).
- Run preflight only when it prevents loading the wrong skill or too many
  skills.
- Do not load every skill just because the task is cinematic.
