# Preflight Router

Use this tiny preflight before loading cinematic skills only when the request is
unclear, broad, or crosses domains.

## Skip Preflight When

- The user names the exact skill or output.
- The task clearly maps to one row in `SKILL_INDEX.md`.
- The user asks for a quick direct output.

## Run Preflight When

- The request says only "make it cinematic", "improve this scene", "make a
  prompt", or similar broad wording.
- The task may need 2+ domains: GPT Image 2, camera, color, acting, sound,
  story, ethics, Seedance.
- The user asks for review but does not say review what.
- Loading the wrong skill would waste context.

## Micro-Preflight

Answer these silently first:

1. What is the final output: image prompt, video prompt, review, shot list,
   rewrite, palette, sound cue, acting note, or character audit?
2. What is the lead domain?
3. Is one skill enough?
4. What is the smallest next file to read?
5. Does the task need a specific model's quirks (GPT Image 2 or Seedance 2.0)?

## Ask At Most One Question

Ask only if routing is still ambiguous. Prefer one short question:

```text
Which area should I focus on first: GPT Image 2, visuals, story, acting, color, sound, or video prompt?
```

If the user does not answer, choose the most likely lead skill and continue.

## Router Output

Keep this internal unless useful:

```text
Lead skill:
Support skill:
Reference file:
Reason:
```

## Reference Selection

After choosing the lead skill, decide which references to load:

- **Start with `GUIDE.md` only.** This is always enough for simple tasks.
- **Add `examples.md`** when the user asks "show me how" or needs a pattern to
  follow.
- **Add `model-quirks.md`** when the task targets GPT Image 2 or Seedance 2.0
  and needs model-specific guidance.
- **Add `advanced-techniques.md`** when the task needs professional-level depth
  or the user hits a problem the core guide does not cover.
- **Add core guides** (`*-guide.md`, `*-framework.md`) when the task needs
  structured vocabulary or review tables.
- Do not load all references at once. Start narrow, add depth only when needed.

## Fallback Rules

- If the final output is an OpenAI-generated image, choose
  `gpt-image-2-photoreal-synthesis` before camera or color.
- If the final output is a Seedance video clip, choose
  `seedance-cinematic-prompt-director` before camera, acting, or color.
- If the user asks only to "make it cinematic", ask one focus question before
  loading multiple skills.
- If still unsure, choose one lead skill and continue. Do not load the whole
  repo.

## Hard Rule

Preflight is a gate, not a work mode. Do not expand into long planning unless
the user asks for planning.
