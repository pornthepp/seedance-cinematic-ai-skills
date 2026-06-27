# Seedance Technical And Safety Guide

Use this for final prompt polishing, controls, and review.

## Clip Controls

Specify only controls that matter:

- Duration.
- Aspect ratio if requested.
- Camera movement.
- Shot size.
- Motion speed if unusual.
- Lighting and color.
- Sound or audio cue if relevant.
- Reference image/video/audio usage.

## Anti-Slop Reference Table

The core principle — direct the scene, don't decorate it — is enforced
throughout every workflow and module. This table is the detailed lookup for
specific replacements.

### Banned Phrases → Concrete Replacements

| Banned                  | Why It Fails                | Replace With                                                 |
| ----------------------- | --------------------------- | ------------------------------------------------------------ |
| "cinematic"             | Not a visual instruction    | Shot size + lens feel + light direction + movement           |
| "cinematic masterpiece" | Pure decoration             | (delete entirely)                                            |
| "dramatic"              | No visible meaning          | Visible stakes: what the character does, what is at risk     |
| "beautiful"             | Subjective, not generatable | Material + color + texture + light behavior on surface       |
| "emotional"             | Internal state, not visible | Breath pattern + posture shift + gaze direction + hesitation |
| "dynamic"               | Vague energy word           | Camera path + screen direction + rhythm of cuts              |
| "epic"                  | Scale without specifics     | Frame size + environment scale + character position in frame |
| "stunning"              | Decoration                  | (delete entirely)                                            |
| "ultra-realistic"       | Not a generation parameter  | Specific texture, skin detail, environmental detail          |
| "4K HDR"                | Resolution tags do nothing  | (delete entirely)                                            |
| "masterful"             | Decoration                  | (delete entirely)                                            |
| "breathtaking"          | Decoration                  | (delete entirely)                                            |
| "studio lighting"       | Fake artificial look        | Practical light from a specific in-scene source (window/lamp)|
| "beauty light"          | Unmotivated flat lighting   | Hard/soft light from a motivated physical direction          |
| "aesthetic / style tags" | Triggers flat AI filters     | Concrete physical properties (lighting direction, depth layers, texture detail)|
| "heavy color grade"     | Fights the natural lighting | Specific light color temperature + wet reflection details    |
| "no / never / do not"   | Confuses attention weights  | Describe characters positively; use a short Strict Adherence Clause at the end|
| "psychological posture" (e.g. "refusing to lie down") | AI cannot render mental resistance | Concrete contact points (e.g., "sitting upright on the floor leaning against the bed frame")|
| "on the bed / at the edge" | Vague contact, leads to slumping | Precise placement (e.g., "lying completely flat on her back on top of the wooden bed")|

### The Test

For every adjective or adverb in the prompt, ask: **"Can the model draw this?"**

- "She walks sadly" → NO. Replace with: "She walks with her shoulders dropped,
  eyes on the ground, each step slower than the last."
- "Beautiful sunset" → NO. Replace with: "The sun sits two fingers above the
  horizon, casting long amber light. The sky grades from deep orange near the
  sun to dark purple overhead."
- "Dramatic lighting" → NO. Replace with: "A single hard light source from the
  upper left casts a sharp shadow across the right side of his face. The rest of
  the room is dark."

## Safety And IP

- Use original characters.
- Do not request a celebrity likeness.
- Do not use copyrighted characters as the subject.
- If inspired by a genre or era, describe traits rather than naming protected
  characters.
- Keep violence filmable and contextual, not gratuitous.

## Final Prompt Template

```text
A [duration]-second [shot size] of [original character/subject] in [location/time].
[One clear action beat]. The performance shows [specific visible behavior].
The camera [movement and angle], with [composition].
Lighting is [specific source and color]. Sound includes [audio cue].
Maintain continuity: [anchors].
```

## Review Checklist

Before submitting any prompt, verify:

- [ ] One main action beat — not two, not three.
- [ ] Character is original and described consistently with prior shots.
- [ ] Camera is concrete: shot size + angle + movement specified.
- [ ] Movement is physically possible within the stated duration.
- [ ] Environment supports the action and is described beyond just the visible
      frame.
- [ ] Audio cue is useful, not decorative.
- [ ] **Zero vague adjectives remain** — no "cinematic," "dramatic,"
      "beautiful," "epic," "stunning."
- [ ] No celebrity or copyrighted character dependency.
- [ ] **No negative clutter in prompt body** — do not use "no," "never," "not" to exclude elements. Use positive descriptions (e.g., "visibly a woman") and place a standard Strict Adherence Clause at the end.
- [ ] **No abstract style tags or grading names** — broken down into light sources, shadow directions, and surface reflections.
- [ ] **Camera blocking is physically plausible** — uses standard camera terminology (e.g., "over-the-shoulder framing").
- [ ] Every descriptor answers the question: "Can the model draw this?"
