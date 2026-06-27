# Seedance Model-Specific Quirks

Knowledge specific to Seedance 2.0 that goes beyond general video prompt
writing. This file covers behaviors, limitations, and techniques that only apply
to this model.

## How Seedance Differs From Other Video Models

Seedance is a video generation model from Bytedance/Doubao that generates short
video clips from text prompts, optionally conditioned on reference images,
audio, or video. It is not a frame interpolation tool or a video-to-video
transformer — it generates novel motion from a text description.

Key differences from image generation:

- **Temporal coherence is the hard problem.** An image prompt only needs to
  describe one moment. A video prompt must describe motion, change, and
  continuity across time.
- **One beat per clip.** Seedance generates short clips (typically 4-15
  seconds). Asking for a complex multi-beat sequence in one clip produces
  confused motion. Split multi-beat scenes into separate shots.
- **Physics simulation is approximate.** The model understands general physics
  (gravity, momentum, fabric behavior) but does not simulate them precisely.
  Complex physical interactions (breaking glass, splashing water, fire behavior)
  are approximate and may look unnatural.

## Duration Sweet Spots

| Duration      | Best For                                                                                   | Risk                                                                                                              |
| ------------- | ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| 4-5 seconds   | Single action, reaction shot, product reveal, mood clip                                    | Very short — must be one focused moment. No time for buildup.                                                     |
| 6-8 seconds   | One emotional beat, one physical action with setup and follow-through, a short camera move | The most reliable range. Enough time for one complete action without overloading.                                 |
| 10-12 seconds | A beat with buildup and resolution, a tracking shot, a dialogue moment                     | Works well if the action is continuous and the camera movement is simple.                                         |
| 13-15 seconds | Extended action, a slow emotional moment, environment reveal                               | Higher risk of temporal drift — character appearance may shift, camera may wander, background details may change. |
| 15+ seconds   | Not recommended                                                                            | Temporal coherence degrades significantly. Split into multiple shots.                                             |

**Default recommendation:** 6-8 seconds unless the scene specifically requires
more time.

## Motion Types — What Works vs. What Struggles

### Works Well

- **Walking, running, turning.** Basic locomotion is reliable. Specify speed and
  style: "walks slowly with heavy steps" vs "jogs lightly."
- **Slow camera movements.** Slow push in, gentle pan, static-to-slow drift.
  These are temporally stable.
- **Facial expressions changing.** A smile forming, a look of surprise, a frown
  deepening — the model handles gradual emotional shifts on faces.
- **Environmental movement.** Wind in hair, rain falling, leaves blowing, smoke
  drifting, water flowing. Natural motion patterns.
- **Simple hand interactions.** Picking up an object, putting something down,
  reaching out. Keep hand actions simple and specify the path.

### Requires Care

- **Fast action.** Quick punches, fast turns, sudden acceleration. The model may
  blur fast motion or skip frames. If you need fast action, keep the clip short
  (4-6 seconds) and describe the motion arc clearly.
- **Multiple characters interacting.** Two people talking works. Two people
  fighting requires very clear spatial description. Three+ characters in the
  same frame with different actions is high risk.
- **Camera + subject movement simultaneously.** If both the camera and the
  subject are moving, specify which is the primary motion source. "The camera
  tracks alongside the running woman" is clearer than "the woman runs while the
  camera follows."
- **Cloth and hair in complex motion.** A coat blowing in wind works. Detailed
  fabric draping during a spin or fall may produce artifacts.

### Struggles

- **Complex hand manipulation.** Typing, playing piano, shuffling cards,
  counting money — fine motor hand actions with multiple fingers are unreliable.
- **Rapid camera changes.** A whip pan, a sudden cut-like zoom, or an abrupt
  camera direction change within one clip tends to produce visual artifacts.
- **Precise choreography.** Dance moves, martial arts sequences with specific
  forms, synchronized group movement. The model generates plausible motion, not
  precise choreography.
- **Physics-dependent action.** Breaking, shattering, exploding, spilling,
  pouring — actions that depend on precise physical simulation are approximate
  at best.
- **Backward motion.** Characters walking backward, objects moving in reverse —
  the model's temporal understanding is forward-biased.

## Camera Movement Specifics

### Reliable Camera Behaviors

| Camera Move      | How To Prompt                                             | Notes                                                                          |
| ---------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Static / locked  | "The camera does not move" or "locked camera"             | Most reliable. Use as default unless movement serves the beat.                 |
| Slow push in     | "The camera slowly pushes in toward [subject]"            | Works well. Specify start and end framing: "from medium shot to close-up."     |
| Slow pull back   | "The camera slowly pulls back to reveal [environment]"    | Works well. Good for reveals.                                                  |
| Pan left/right   | "The camera pans slowly to the right to follow [subject]" | Specify speed ("slowly") and reason (following subject or revealing space).    |
| Tracking / dolly | "The camera tracks alongside [subject] at the same speed" | Works best with simple lateral movement.                                       |
| Slight handheld  | "Slight handheld camera shake"                            | Adds realism. Do not combine with other camera movements — it becomes chaotic. |

### Unreliable Camera Behaviors

| Camera Move                  | Problem                                                                                                          | Alternative                                                                             |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| Crane / jib (vertical sweep) | Vertical camera movement is less stable than horizontal. Objects may warp during the vertical transition.        | Use a high-angle static shot or a low-angle static shot instead of moving between them. |
| 360-degree orbit             | Full rotation produces temporal inconsistencies — the background may not match when the camera returns to start. | Use a partial orbit (90-120 degrees maximum).                                           |
| Whip pan                     | Too fast for clean generation. Produces blur artifacts.                                                          | Cut to a new shot instead.                                                              |
| Zoom (vs. dolly)             | Zoom changes perspective in ways the model handles poorly.                                                       | Use dolly/push instead of zoom. Describe camera position change, not lens change.       |
| Dutch angle (tilted)         | May revert to level during the clip.                                                                             | If you need a tilted frame, make it subtle and combine with a static camera.            |

## Reference Input Usage

Seedance can accept reference inputs to condition generation:

### Image Reference

- **Character consistency.** Provide a reference image of the character. The
  model will attempt to maintain appearance (face, clothing, build) in the
  generated video.
- **Style reference.** A reference image can set the visual tone (lighting,
  color palette, atmosphere).
- **Limitations:** The reference is an influence, not a guarantee. Complex
  outfits or unusual features may drift from the reference. Reinforce key visual
  details in the text prompt even when using an image reference.

### Audio Reference

- **Rhythm matching.** The model can sync motion to audio rhythm — useful for
  music videos, dance clips, and action with a beat.
- **Ambient matching.** Audio can set the energy level and mood, influencing the
  pacing and intensity of generated motion.
- **Limitations:** Audio influence is suggestive, not frame-accurate. Do not
  expect precise lip-sync or beat-matched choreography. The model captures
  general rhythm and energy.

### Video Reference

- **Motion reference.** A source video can guide the type of movement, pacing,
  and camera behavior.
- **Limitations:** The model does not copy the source frame-by-frame. It uses
  the reference as a motion guide. Highly specific motion (signature dance
  moves, exact fight choreography) will be approximated, not replicated.

## Known Artifacts and Workarounds

| Artifact                 | When It Happens                                                       | Workaround                                                                                                                                                          |
| ------------------------ | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Character face drift     | Clips longer than 10 seconds, profile-to-front turns                  | Keep clips under 10 seconds for face-critical shots. Avoid full head turns — use 3/4 angle to 3/4 angle instead.                                                    |
| Finger multiplication    | Hands in motion, gripping, reaching                                   | Specify simple hand states: "hands at sides," "hand in pocket," "one hand resting on table."                                                                        |
| Background inconsistency | Camera movement reveals new background areas                          | Describe the full environment, not just what's initially visible. "The alley extends behind the camera with more brick walls and fire escapes."                     |
| Temporal jitter          | Static elements vibrating or shifting slightly                        | Specify "locked camera" and "static background" when the environment should not move.                                                                               |
| Clothing morph           | Loose clothing during fast motion                                     | Describe clothing fit: "fitted jacket" is more stable than "flowing cape." Reduce motion speed.                                                                     |
| Motion freeze            | End of longer clips where the model runs out of coherent motion       | Keep the action shorter than the clip duration. For a 10-second clip, the main action should complete by second 7-8, with the remaining time as a hold or settling. |
| Physics glitches         | Objects defying gravity, impossible reflections, water flowing upward | Describe physics expectations: "the object falls and bounces once." Keep physics-dependent moments short.                                                           |

## Multi-Script and Localization

- Seedance prompts should be in English for best results — the model's text
  understanding is strongest in English.
- Thai, Chinese, Japanese, and Korean prompts can work but may lose nuance in
  complex spatial or motion descriptions.
- **Translation strategy:** If the user provides input in Thai or another
  language, translate the creative intent into precise English while preserving
  the emotional and cultural specificity. Do not literally translate — adapt the
  description for the model's English understanding.

## Prompt Length and Structure

- **Optimal prompt length:** 50-150 words. Shorter prompts lack specificity;
  longer prompts may overload temporal planning.
- **Structure matters:** Front-load the subject and action. Camera and lighting
  details come after the core action is described.
- **One paragraph works better than bullet lists** — the model reads the prompt
  as natural language, not structured data.

## Combining With Other Skills

When using Seedance with other cinematic skills:

- **Camera skill → Seedance:** Translate shot design vocabulary into
  Seedance-friendly language. Replace "85mm telephoto compression" with "the
  camera is far from the subject, compressing the background against the
  foreground."
- **Acting skill → Seedance:** Translate actor direction into visible behavior
  description. The model cannot interpret "use Meisner technique" — but it can
  execute "she listens to him speak, her expression shifts from neutral to a
  slight frown, her hand tightens on the table edge."
- **Color skill → Seedance:** Describe lighting and color in physical terms, not
  grade terms. "Warm amber light from the left" works. "Lifted blacks with
  desaturated midtones" does not — that is post-production language the model
  cannot execute.
