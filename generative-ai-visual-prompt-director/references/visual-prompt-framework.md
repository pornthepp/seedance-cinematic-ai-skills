# Visual Prompt Framework

Use this framework to turn a visual brief into a clear, platform-neutral prompt.
Use [visual-language.md](visual-language.md) when choosing exact visual terms.

## Core Principle

A prompt is a hierarchy of visible decisions, not a bag of attractive words.
Describe what must be seen first, then how it is staged, photographed, lit, and
felt. Every phrase should change the image or motion in a useful way.

## 1. Build the Brief

Resolve these inputs before writing the final prompt:

- **Purpose:** what the visual must communicate or make the audience feel.
- **Subject:** identity, count, age or type, defining features, wardrobe, props.
- **Action:** one readable action or state for an image; one filmable beat for a
  video.
- **Environment:** place, time, weather, period, and story-relevant details.
- **Priority:** the one element that must survive if the model simplifies the
  request.
- **Constraints:** required objects, forbidden content, framing, continuity,
  text-safe space, or delivery format.
- **Target:** image or video, aspect ratio, duration, and platform when known.

Ask only for missing information that would materially change the result. When
the user wants exploration, state reasonable assumptions and provide controlled
alternatives instead of blocking on every detail.

## 2. Establish the Visual Hierarchy

Rank prompt content in this order:

1. Primary subject and defining identity
2. Readable action or emotional state
3. Subject-environment relationship
4. Composition and camera viewpoint
5. Lighting and color logic
6. Material, texture, and finish
7. Mood and stylistic treatment
8. Motion and continuity, for video
9. Exclusions and delivery constraints

Put decisive information early. Keep secondary decoration late. Do not give
equal verbal weight to ten competing ideas.

## 3. Write in Visible Language

Convert abstract goals into observable evidence.

| Abstract request | Visible direction |
| --- | --- |
| lonely | one small figure, wide empty frame, distant horizon, no crowd |
| powerful | low camera, upright posture, centered placement, hard backlight |
| intimate | close framing, shallow depth, soft side light, restrained movement |
| chaotic | competing diagonals, crowded layers, irregular motion, broken light |
| premium | precise geometry, controlled reflections, refined material detail |

Prefer concrete nouns, active verbs, spatial relationships, and physical light.
Avoid filler such as `beautiful`, `amazing`, `high quality`, or several mood
adjectives that do not describe visible evidence.

## 4. Assemble the Prompt

### Image Prompt

```text
[primary subject and defining traits], [one readable action or state],
[environment and time], [shot size and viewpoint], [composition and depth],
[lens feeling], [motivated lighting], [color relationships],
[materials and textures], [visible mood cues], [required constraints].
Exclude: [only elements that are likely and harmful].
```

### Video Prompt

```text
Starting frame: [subject, environment, composition, and state].
Action: [one filmable beat with direction and pace].
Camera: [movement, speed, and relationship to the subject].
Environment motion: [wind, particles, crowd, water, light, or stillness].
Ending frame: [clear visual change or resolved state].
Continuity: [identity, wardrobe, props, screen direction, light, and geography].
Constraints: [duration, framing, forbidden events, or delivery needs].
```

For short clips, one strong action is more reliable than a chain of events.
Describe the start, change, and end rather than using vague directions such as
`make it cinematic` or `add dynamic motion`.

## 5. Use References by Role

Assign each reference one job. Do not assume a reference automatically controls every property.

| Reference role | What to preserve | What may change |
| --- | --- | --- |
| Identity | face, silhouette, product geometry, signature markings | pose, scene, light |
| Content | object or subject category and key attributes | style, composition |
| Composition | placement, camera position, scale, negative space | identity, finish |
| Style | palette, medium, texture, contrast, rendering character | subject and action |

### The Ref-over-Text Rule (Precedence of Visual References)

#### Core Principle
The reference image controls all **physical details** (structure, geography, materials, character identity, textures). The text prompt should only specify actions, camera directions, lighting, or details that the reference image cannot convey. If the text prompt contradicts or over-describes details present in the reference image, autoregressive or diffusion models with adapter layers (e.g., IP-Adapter, ControlNet) prioritize the reference's visual features, ignoring text commands or causing styling/rendering errors.

#### What the Reference Controls (Do NOT repeat or describe in text)
- **Structure, Materials & Architecture:** e.g., stone walls, wood, bamboo, roof, arched stone doorway.
- **Environment & Geography:** e.g., jungle, river, mountain, dock, specific trees.
- **Color Palette & Tonal Range:** e.g., overall hue bias, saturation logic.
- **Character Attributes & Identity:** e.g., face, hair style/color, skin tone, body proportions, clothing/armor.
- **Textures & Surface Finishes:** e.g., scales, leather, fabric weave, steel plates.

#### What the Text Prompt Controls (What references cannot do)
- **Pose, Action & Blocking:** e.g., kneeling, sitting, running.
- **Camera Settings & Composition:** e.g., shot size, camera height, lens millimeter, camera angle.
- **Lighting Direction & Quality:** e.g., key light direction, shadow sharpness (hard vs. soft shadow edges).
- **Atmospheric/Weather Effects:** e.g., rain, wind, mist not visible in the reference.
- **Performance & Expression:** e.g., looking astonished, breathing heavily, smiling.
- **Hands & Anatomy Correction:** e.g., specifying hand placement and finger count to prevent AI hand anomalies.
- **Style Override:** If the reference is a 2D illustration or CGI render, but the project requires cinematic photorealism, you *must* explicitly force a style override in the prompt.

#### Style Override Protocol
When using reference images that are illustrations, 2D art, or CGI renders, models often copy the rendering style instead of producing a photorealistic image. To prevent this, include a clear override declaration in the reference inputs:

```text
References define physical details only — face, body, costume, structure, proportions.
Do NOT copy the rendering style or art style from the references.
Render all panels as cinematic photorealistic — as if shot on 35mm film
with a real camera, real skin, real fabric, real light.
Not illustration, not digital painting, not 2D, not CGI render.
```

#### Formatting REFERENCE INPUTS
Structure the reference declaration block exactly as follows:

```text
REFERENCE INPUTS:
[filename.jpg] = {placeholder_name}
References define physical details only — face, body, costume, structure, proportions.
Do NOT copy the rendering style or art style from the references.
Render all panels as cinematic photorealistic — as if shot on 35mm film
with a real camera, real skin, real fabric, real light.
Not illustration, not digital painting, not 2D, not CGI render.
```
- **Mapping:** Map the filename to its descriptive placeholder (e.g., `image1.jpg = {warrior_armor}`).
- **Roles:** If references serve distinct purposes, add concise roles (e.g., `{warrior_armor} defines the battle robe being removed`).

#### Strict Rules (Avoid Overriding)
- **No Redundancy:** Do not describe materials or environments already depicted in the reference (e.g., do not write "bamboo walls" when the reference shows stone walls, or "dark jungle" when the reference shows a river bank).
- **No Attire/Feature Redundancy:** Do not repeat character features unless they change state relative to the reference.
- **Referencing Protocol:** Cite the placeholder directly with minimal text:
  - *Correct:* "the hut as shown in {hut_ref}" or "Inside {hut_ref}"
  - *Incorrect:* "Inside a dark bamboo hut with rough wooden walls and a dirt floor..."

When several references conflict, declare the priority. For continuity-critical work, repeat stable identity anchors in text and keep wardrobe, props, lighting, and screen direction explicit.

## 6. Check for Prompt Conflicts

Remove or resolve:

- incompatible treatments, such as flat graphic shading plus realistic skin
  detail without a clear hybrid rule;
- opposing light directions or times of day;
- a close shot that also demands a vast environment as equally important;
- multiple simultaneous actions that cannot read in one frame;
- camera motion that contradicts a locked or static viewpoint;
- mood words unsupported by composition, light, color, or performance;
- redundant synonyms that dilute priority;
- named imitation of a living artist when visual attributes can express the
  intent.

## 7. Refine by Diagnosis

Change one decision family at a time so the cause of improvement remains clear.

| Failure | First adjustment |
| --- | --- |
| Wrong subject | strengthen identity anchors; remove competing subjects |
| Weak action | replace abstract intent with one visible verb and body cue |
| Confused frame | simplify hierarchy; specify shot size and placement |
| Wrong viewpoint | state camera height, angle, and subject direction together |
| Flat image | add foreground/midground/background or light separation |
| Wrong mood | change visible cues before adding more mood adjectives |
| Plastic materials | name surface, roughness, wear, and reflection behavior |
| Video drifts | reduce events; lock continuity anchors and ending state |
| Motion feels random | define subject motion, camera motion, and environment motion separately |

Keep a successful prompt as the control. Create variants by changing only one
axis: composition, camera, light, color, material, mood, or motion.

## Final Review

Before delivery, confirm:

- The main subject and action are unambiguous.
- The environment supports rather than competes with the subject.
- Composition, camera, and lens feeling serve the intended emotion.
- Light has a plausible source, direction, quality, and contrast.
- Color and material descriptions are specific enough to render.
- Mood is expressed through visible evidence.
- Video includes a readable change and continuity anchors.
- Constraints are concise and do not fight the desired result.
- Platform-specific syntax is added only after checking current documentation.

