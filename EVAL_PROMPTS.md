# Router Evaluation Prompts

Use this file only to test whether the skill router chooses the right file. Do not load it during normal work.

## Expected Routing — Skill Selection

| Test Prompt | Expected Lead Skill |
|---|---|
| Write a photoreal GPT Image 2 prompt for a luxury watch on black glass. | `gpt-image-2-photoreal-synthesis` |
| Rewrite this OpenAI image prompt so the product label text is more reliable. | `gpt-image-2-photoreal-synthesis` |
| Make this image prompt more cinematic with stronger framing and lens choice. | `cinematic-camera-composition-director` |
| Design a restrained color palette for a lonely night bus scene. | `cinematic-color-look-development` |
| Create a Seedance 2.0 prompt for a 10-second chase through a wet alley. | `seedance-cinematic-prompt-director` |
| Split this long video idea into consistent Seedance storyboard shots. | `seedance-cinematic-prompt-director` |
| Give actor notes for a character who is hiding panic during a job interview. | `modern-acting-performance-mastery` |
| Review this short film script for festival-level narrative clarity. | `short-film-artistic-narrative-analysis` |
| Build a sound cue plan for the moment before a confession. | `cinematic-music-soundscape-design` |
| Audit this character group for cultural stereotypes and agency issues. | `ethical-character-representation` |
| Make it cinematic. | `PREFLIGHT_ROUTER.md`, then ask one focus question |

## Expected Routing — Reference Depth

| Test Prompt | Expected Skill | Expected Reference |
|---|---|---|
| Show me an example of a good GPT Image 2 product prompt. | `gpt-image-2-photoreal-synthesis` | `references/examples.md` |
| Why does GPT Image 2 keep adding extra fingers to my portraits? | `gpt-image-2-photoreal-synthesis` | `references/model-quirks.md` |
| My Seedance prompt has too many actions. Fix it and show me how. | `seedance-cinematic-prompt-director` | `references/examples.md` |
| What duration works best for Seedance action clips? | `seedance-cinematic-prompt-director` | `references/model-quirks.md` |
| My shot sequence all looks the same. What am I doing wrong? | `cinematic-camera-composition-director` | `references/advanced-techniques.md` |
| Show me how to turn a vague shot request into a proper camera direction. | `cinematic-camera-composition-director` | `references/examples.md` |
| I graded my whole film teal and orange but the skin tones look dead. | `cinematic-color-look-development` | `references/advanced-techniques.md` |
| What does a real DI session workflow look like? | `cinematic-color-look-development` | `references/advanced-techniques.md` |
| Show me how to design sound for a tension scene without music. | `cinematic-music-soundscape-design` | `references/examples.md` |
| What frequency range should I use for dread? | `cinematic-music-soundscape-design` | `references/advanced-techniques.md` |
| My character direction just says "be sad." How do I fix this for an AI video prompt? | `modern-acting-performance-mastery` | `references/examples.md` |
| What is the mask-and-leak technique? | `modern-acting-performance-mastery` | `references/advanced-techniques.md` |
| My 7-minute short film feels like it drags. Why? | `short-film-artistic-narrative-analysis` | `references/examples.md` or `references/advanced-techniques.md` |
| What do festival juries actually look for in a short film? | `short-film-artistic-narrative-analysis` | `references/advanced-techniques.md` |
| Score this cast of 5 characters on the representation rubric. | `ethical-character-representation` | `references/representation-review-guide.md` |
| Check my horror script for genre-specific representation red flags. | `ethical-character-representation` | `references/representation-review-guide.md` |

## Pass Criteria

- The router picks one lead skill first.
- It opens a support skill only when the output needs it.
- It does not load all cinematic skills.
- It does not use Stable Diffusion or Midjourney syntax for GPT Image 2 tasks.
- It asks at most one question for vague requests.
- It loads examples only when the user asks for demonstrations or the task needs a pattern.
- It loads model quirks only when the task targets GPT Image 2 or Seedance 2.0 specifically.
- It loads advanced techniques only when the task needs depth beyond the core workflow.
- It does not load every reference file for every task.
