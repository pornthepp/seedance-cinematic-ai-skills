# Cinematic Skill Collection

Language: **English** | [Thai](README.th.md)

A set of creative-direction skills that help AI agents work on cinematic projects — from writing image prompts to directing acting, designing color palettes, planning sound, and more. Each skill is a focused workflow that the agent loads only when it needs it.

## What's Inside

**8 skills** covering the main areas of cinematic creative work:

| Skill | What It Helps With |
|---|---|
| `cinematic-camera-composition-director` | Camera angles, shot sizes, lens choices, storyboards, framing |
| `gpt-image-2-photoreal-synthesis` | Writing text prompts for realistic GPT Image 2 photos — products, portraits, editorial, typography |
| `cinematic-color-look-development` | Color palettes, look development, lighting logic, color grading notes |
| `cinematic-music-soundscape-design` | Music direction, sound effects, silence, ambience planning |
| `short-film-artistic-narrative-analysis` | Short film script critique, story structure, festival prep |
| `seedance-cinematic-prompt-director` | Writing video prompts for Seedance 2.0 — action clips, storyboard sequences, commercials, music videos, educational content, with strict anti-slop quality enforcement |
| `modern-acting-performance-mastery` | Actor direction, emotional beats, dialogue delivery, body/voice choices |
| `ethical-character-representation` | Checking characters for stereotypes, bias, agency, and cultural specificity |

**3 routing files** that help the agent pick the right skill:

- `SKILL_INDEX.md` — look up which skill to use for a given task
- `PREFLIGHT_ROUTER.md` — figure out what to do when the request is vague (like "make it cinematic")
- `EVAL_PROMPTS.md` — test prompts to check that the router is working correctly

## How It Works



1. A request comes in.
2. If it's clear what skill to use, go straight to `SKILL_INDEX.md` and pick one.
3. If it's vague, run `PREFLIGHT_ROUTER.md` to narrow it down — it asks at most one question.
4. Load the skill's `SKILL.md` and follow the workflow.
5. If the task needs more depth, open a specific reference file — never load everything at once.

## What Each Skill Folder Contains

Every skill folder has the same structure:

```text
skill-name/
  SKILL.md              ← Start here. Short workflow + quality gate.
  references/
    core-guide.md       ← Vocabulary, checklists, review tables
    examples.md         ← Full input → output worked examples
    model-quirks.md     ← Model-specific tips (GPT Image 2 / Seedance only)
    advanced-techniques.md  ← Professional-level depth
```

Not every skill has every reference type. Here's what's available:

| Skill | Core Guide | Examples | Model Quirks | Advanced |
|---|---|---|---|---|
| Camera | shot-composition-guide, camera-workflow | 3 examples | — | sequence failures, lens psychology, blocking |
| GPT Image 2 | photoreal-prompt-framework, visual-refinement-loop | 3 examples | typography, multi-turn editing, artifacts | — |
| Color | look-development-guide | 3 examples | — | grading mistakes, DI workflow, transition theory |
| Sound | soundscape-guide | 3 examples | — | frequency map, silence types, spotting mistakes |
| Short Film | short-film-analysis-guide | 3 examples | — | pressure cooker model, ending taxonomy, festival heuristics |
| Seedance | storyboard-workflow, scene-modules (action, chase, horror, romance, dialogue, product, commercial, music video, educational), technical-and-safety | 3 examples | duration sweet spots, motion types, camera limits, artifacts | — |
| Acting | acting-methods-index, performance-direction-guide | 3 examples | — | AI direction failures, mask/leak, status transactions |
| Ethics | representation-review-guide (with scoring rubric + genre checklists) | 3 examples | — | — |

## Quick Start

**If you're an AI agent:** Read `SKILL_INDEX.md` first. It tells you which skill to load for any given task. Only open references when the task needs them.

**If you're a human:** Browse any `SKILL.md` for a quick creative checklist. Check `references/examples.md` for full demonstrations of what each skill produces.

## Installation

Copy the skill folders you need into your AI agent's skill directory, or use this whole repo as a skill reference.

## Key Design Decisions

- **GPT Image 2 skill** is for writing text prompts only — no API code, no Stable Diffusion syntax, no Midjourney parameters. Those tools have their own syntax that shouldn't be mixed in.
- **Seedance skill** covers Seedance 2.0 specifically — including which durations work best, what types of motion are reliable, what camera moves to avoid, and a strict "Direct the scene, don't decorate it" anti-slop system that bans vague words like "cinematic" or "dramatic" and forces concrete film direction instead.
- **Seedance scene modules** include templates for action, chase, horror, romance, dialogue, product, commercial & product promo, music video with rhythm sync, and educational & explainer content.
- **Ethics skill** includes a 1-5 scoring rubric and genre-specific red flag checklists (action, horror, romance, sci-fi, drama) — not just generic "be inclusive" advice.
- **Worked examples** in every skill show real input → output transformations, so you can see exactly what the skill produces.
- **Model quirks** files document behaviors specific to GPT Image 2 and Seedance 2.0 that you won't find in general prompt-writing guides.
