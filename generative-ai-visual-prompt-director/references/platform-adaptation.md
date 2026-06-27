# Platform Adaptation

Use this reference after the visual intent is clear. Preserve the creative
decision; translate only how the target system receives it.

## Start With A Capability Brief

Before adapting, identify:

- family: natural-language, parameter-driven, local/node, or video
- accepted inputs: text, image reference, mask, pose, depth, audio, or timeline
- exposed controls: dimensions, variation, reproducibility, guidance, motion,
  duration, and output count
- limits: prompt length, input size, generation duration, safety rules, and
  unsupported controls

Never invent a control. If a capability is unknown, keep the instruction in
plain language and label the uncertainty.

## Keep An Intent Spine

Carry these invariants across every family:

1. subject and visible action
2. environment and time
3. composition and camera relationship
4. lighting and color behavior
5. material or surface cues
6. mood and story beat
7. continuity anchors
8. exclusions that prevent a likely failure

Platform controls may change. The intent spine should not.

## Family 1: Natural-Language Systems

Write one ordered visual description:

```text
[subject/action], [environment/time], [composition/camera], [light/color],
[materials/details], [mood], [continuity anchors], [important exclusions].
```

- Put identity and composition before decorative style.
- Prefer visible evidence over abstract adjectives.
- Use short sentences when several relationships must remain distinct.
- Do not append parameter-like tokens unless the system documents them.

## Family 2: Parameter-Driven Systems

Separate semantic content from generation controls:

```text
Prompt: [intent spine in natural language]
Controls:
  aspect ratio: [story-driven ratio]
  variation strength: [low, medium, or high]
  reproducibility: [fixed or exploratory]
  reference influence: [only if supported]
```

- Map only documented controls.
- State values as labeled fields, not vendor-specific command syntax.
- Keep camera, lighting, and performance in the prompt unless the system has a
  dedicated control for them.
- Explain the creative consequence of each non-default value.

## Family 3: Local Or Node-Based Workflows

Translate the intent into stages rather than one overloaded text field:

1. model and version
2. positive visual conditioning
3. optional exclusions or negative conditioning
4. composition, pose, depth, or reference conditioning
5. dimensions and reproducibility settings
6. sampling or refinement stage
7. upscale, color, and delivery stage

Record the model version, graph version, inputs, dimensions, reproducibility
state, and changed node for every comparison. Treat optional conditioning as a
diagnostic tool, not a place to repeat the whole prompt.

## Family 4: Video Systems

Convert a still-image description into a timed, filmable beat:

```text
Duration: [short practical duration]
Opening state: [subject, pose, environment]
Action: [one primary action with beginning, middle, end]
Camera: [framing, movement, speed]
Environment motion: [one or two supporting motions]
Performance: [visible behavior]
Continuity: [identity, wardrobe, props, screen direction, light]
Ending state: [clear final pose or composition]
```

- Use one dominant subject action and one dominant camera move.
- Describe change over time; do not merely add “cinematic motion” to a still
  prompt.
- Remove simultaneous instructions that compete for the same subject or camera.
- For multi-shot work, generate or describe each shot separately and define the
  handoff between ending and opening states.

## Portability Check

Before delivery, verify:

- the result still works after all platform controls are removed
- every control is documented for the target family
- no command token, model name, or interface label is assumed universal
- references have a stated purpose: identity, pose, composition, palette, or
  motion
- unsupported precision is expressed as a goal, not a guarantee

## Adaptation Handoff

```text
Target family:
Intent spine:
Supported inputs and controls:
Adapted prompt or workflow:
Controls used and why:
Known limits or uncertainties:
First test to run:
```
