# Cinematic Skill Collection

Language: **English** | [Thai](README.th.md)

A set of creative-direction skills that help AI agents work on cinematic projects — from writing image prompts to directing acting, designing color palettes, planning sound, and more. Each skill is a focused workflow that the agent loads automatically when it needs it.

## What's Inside

**9 skills** covering the main areas of cinematic creative work:

| Skill                                    | What It Helps With                                                                                                                                                     |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `generative-ai-visual-prompt-director`  | Turning a complete visual brief into a platform-neutral AI image or video prompt, adapting concepts across platform families, and troubleshooting weak results |
| `cinematic-camera-composition-director`  | Camera angles, shot sizes, lens choices, storyboards, framing                                                                                                          |
| `gpt-image-2-photoreal-synthesis`        | Writing text prompts for realistic GPT Image 2 photos — products, portraits, editorial, typography                                                                     |
| `cinematic-color-look-development`       | Color palettes, look development, lighting logic, color grading notes                                                                                                  |
| `cinematic-music-soundscape-design`      | Music direction, sound effects, silence, ambience planning                                                                                                             |
| `short-film-artistic-narrative-analysis` | Short film script critique, story structure, festival prep                                                                                                             |
| `seedance-cinematic-prompt-director`     | Writing video prompts for Seedance 2.0 — action clips, storyboard sequences, commercials, music videos, educational content, with strict anti-slop quality enforcement |
| `modern-acting-performance-mastery`      | Actor direction, emotional beats, dialogue delivery, body/voice choices                                                                                                |
| `ethical-character-representation`       | Checking characters for stereotypes, bias, agency, and cultural specificity                                                                                            |

## How It Works

This repository uses Gemini's native **Customizations (Skills) Auto-Discovery** mechanism:
1. Every skill is placed in its own folder at the root level of the project.
2. Inside each folder is a `SKILL.md` file containing YAML frontmatter (`name` and `description`).
3. When the AI agent receives a task, the platform scans the project root, matches the prompt to a skill's description, and automatically loads only the relevant `SKILL.md` instructions.
4. If a task requires more details, the agent opens specific reference files within that skill's folder — preventing the context window from becoming overloaded.

## Folder Structure

Each skill folder follows a clean, modular structure:

```text
[skill-folder-name]/
  SKILL.md            ← Entry point. Frontmatter + core workflow + quality gate.
  templates/
    output-template.md  ← Blank template to fill in
  references/
    core-guide.md       ← Vocabulary, checklists, review tables
    examples.md         ← Full input → output worked examples
    model-quirks.md     ← Model-specific tips (GPT Image 2 / Seedance only)
    advanced-techniques.md  ← Professional-level depth
```

Not every skill has every reference type. Here's what's available:

| Skill       | Core Guide                                                                                                                                         | Examples   | Model Quirks                                                 | Advanced                                                    |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ------------------------------------------------------------ | ----------------------------------------------------------- |
| Gen AI      | visual-prompt-framework, visual-language                                                                                                           | 3 examples | —                                                            | platform-adaptation, iteration-and-troubleshooting          |
| Camera      | shot-composition-guide, camera-workflow                                                                                                            | 3 examples | —                                                            | sequence failures, lens psychology, blocking                |
| GPT Image 2 | photoreal-prompt-framework, visual-refinement-loop                                                                                                 | 3 examples | typography, multi-turn editing, artifacts                    | —                                                           |
| Color       | look-development-guide                                                                                                                             | 3 examples | —                                                            | grading mistakes, DI workflow, transition theory            |
| Sound       | soundscape-guide                                                                                                                                   | 3 examples | —                                                            | frequency map, silence types, spotting mistakes             |
| Short Film  | short-film-analysis-guide                                                                                                                          | 3 examples | —                                                            | pressure cooker model, ending taxonomy, festival heuristics |
| Seedance    | storyboard-workflow, scene-modules (action, chase, horror, romance, dialogue, product, commercial, music video, educational), technical-and-safety | 3 examples | duration sweet spots, motion types, camera limits, artifacts | —                                                           |
| Acting      | acting-methods-index, performance-direction-guide                                                                                                  | 3 examples | —                                                            | AI direction failures, mask/leak, status transactions       |
| Ethics      | representation-review-guide (with scoring rubric + genre checklists)                                                                               | 3 examples | —                                                            | —                                                           |

## Quick Start

**If you're an AI agent:** Since skills are in the project root, the platform will automatically load the right `SKILL.md` based on your task. Follow the instructions and only load the specific references from the skill's folder when you need deeper knowledge.

**If you're a human:** Browse any `[skill-name]/SKILL.md` for a quick creative checklist. Check `[skill-name]/references/examples.md` for full demonstrations of what each skill produces.

## Installation

Copy the skill folders you need into your AI agent's skill directory, or use this whole repo as a skill reference directory.

## Key Design Decisions

- **Auto-Discovery Ready**: Configured for native auto-discovery. Every skill is located at the project root with its own `SKILL.md` file, making it faster and more lightweight for agents to trigger.
- **Ref-over-Text Rule**: Integrates the "Ref-over-Text" rule across general prompting workflows, establishing that visual attributes from references take precedence over text. Encourages minimal, non-conflicting, and non-redundant text prompts when using image references.
- **GPT Image 2 skill** is for writing text prompts only — no API code, no Stable Diffusion syntax, no Midjourney parameters.
- **Seedance skill** covers Seedance 2.0 specifically — including which durations work best, what types of motion are reliable, what camera moves to avoid, and a strict "Direct the scene, don't decorate it" anti-slop system that bans vague words like "cinematic" or "dramatic" and forces concrete film direction instead.
- **Seedance scene modules** include templates for action, chase, horror, romance, dialogue, product, commercial & product promo, music video with rhythm sync, and educational & explainer content.
- **Ethics skill** includes a 1-5 scoring rubric and genre-specific red flag checklists (action, horror, romance, sci-fi, drama) — not just generic "be inclusive" advice.
- **Worked examples** in every skill show real input → output transformations, so you can see exactly what the skill produces.
- **Model quirks** files document behaviors specific to GPT Image 2 and Seedance 2.0 that you won't find in general prompt-writing guides.
