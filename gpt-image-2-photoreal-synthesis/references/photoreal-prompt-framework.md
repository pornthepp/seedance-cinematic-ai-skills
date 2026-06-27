# Photoreal Prompt Framework

Use this when building the final image prompt.

## Six-Part Blueprint

Write a complete production brief, integrating instructions from other cinematic skills when appropriate:

1. **Subject and action:** Describe physical, playable actions, posture, joint/limb contact points, and gaze.
   * *See: [performance-direction-guide.md](../../modern-acting-performance-mastery/references/performance-direction-guide.md) for character physical behavior, expressions, and posture rules.*
   * *See: [representation-review-guide.md](../../ethical-character-representation/references/representation-review-guide.md) for gender-safe, historical, and culturally accurate character descriptions.*
2. **Material, surface, body, product, or identity details:** Textures, wrinkles, skin pores, fabric weave.
3. **Environment and context:** Time, weather, background depth, atmospheric haze.
4. **Lighting setup:** Specify motivated light sources (practical lights, windows) rather than abstract modifiers.
   * *See: [advanced-techniques.md](../../cinematic-color-look-development/references/advanced-techniques.md) for light source setups, three-zone grading, and skin protection.*
5. **Camera, lens feeling, angle, framing, and composition:** Standard cinematic blocking, shot size, lens millimeter, camera height.
   * *See: [shot-composition-guide.md](../../cinematic-camera-composition-director/references/shot-composition-guide.md) for standard camera layouts (e.g., over-the-shoulder).*
   * *See: [advanced-techniques.md](../../cinematic-camera-composition-director/references/advanced-techniques.md) for camera height, depth layers, and blocking rules.*
6. **Color, mood, realistic imperfections, and exact text:** Film grain, desaturated/restrained color palettes, exact quoted text.

## Prompt Rules

- Put the most important requirement first.
- Use complete sentences, not tag soup.
- Keep one main visual idea per image.
- Limit adjectives; prefer concrete nouns and visible details.
- Name spatial placement when layout matters.
- For exact text, quote it and state where it appears.
- Request strict adherence in plain language when the prompt must stay
  controlled.

## Character Posture and Physical Contact

To prevent the AI from generating awkward, slumping, or incorrect character poses (e.g., sliding off furniture or floating):

- **Define Exact Contact Points and Gravity:** Specify exactly what parts of the character's body are touching which surfaces. Use precise physical descriptions (e.g., "lying completely flat on her back on top of the wooden bed" instead of "lying on the bed edge" or "refusing to lie down").
- **Avoid Psychological or Negative Descriptors for Posture:** AI models do not understand negation or psychological states (e.g., "refusing to lie down"). Translate these intentions into concrete physical postures (e.g., "sitting rigidly upright on the floor, leaning her back against the wooden bed frame").
- **Specify Joint and Limb Placements:** Describe what the limbs are doing to anchor the pose (e.g., "kneeling on both knees on the dirt floor, with her palms flat on the ground" or "lying flat with arms rested at her sides").

## The Ref-over-Text Rule (Reference Precedence)

### Core Principle
The reference image controls all **physical details** (structure, geography, and appearance). The text prompt should only specify actions, camera directions, lighting, or details that the reference image cannot convey. GPT Image 2 is an autoregressive model; if the text prompt contradicts or over-describes details present in the reference image, the model prioritizes the text description. This overrides the reference, leading to identity drift, environment mismatch, and style copying.

### Reference Controls (Do NOT repeat or describe in text)
- **Structure, Materials & Architecture:** e.g., stone walls, wood, bamboo, roof, arched stone doorway.
- **Environment & Geography:** e.g., jungle, river, mountain, dock, specific trees.
- **Color Palette & Tonal Range:** e.g., overall hue bias, saturation logic.
- **Character Attributes & Identity:** e.g., face, hair style/color, skin tone, body proportions, clothing/armor.
- **Textures & Surface Finishes:** e.g., scales, leather, fabric weave, steel plates.

### Text Prompt Controls (What references cannot do)
- **Pose, Action & Blocking:** e.g., kneeling, sitting, running.
- **Camera Settings & Composition:** e.g., shot size, camera height, lens millimeter, camera angle.
- **Lighting Direction & Quality:** e.g., key light direction, shadow sharpness (hard vs. soft shadow edges).
- **Atmospheric/Weather Effects:** e.g., rain, wind, mist not visible in the reference.
- **Performance & Expression:** e.g., looking astonished, breathing heavily, smiling.
- **Hands & Anatomy Correction:** e.g., specifying hand placement and finger count to prevent AI hand anomalies.
- **Style Override:** If the reference is a 2D illustration or CGI render, but the project requires cinematic photorealism, you *must* explicitly force a style override in the prompt.

### Style Override Protocol (Critical for Photorealism)
When using reference images that are illustrations, 2D art, or CGI renders, GPT Image 2 will incorrectly copy the rendering style instead of producing a photorealistic image. To prevent this, you **must** include the following override text in your reference inputs:

```text
References define physical details only — face, body, costume, structure, proportions.
Do NOT copy the rendering style or art style from the references.
Render all panels as cinematic photorealistic — as if shot on 35mm film
with a real camera, real skin, real fabric, real light.
Not illustration, not digital painting, not 2D, not CGI render.
```

### Formatting REFERENCE INPUTS
In the prompt generation phase, structure the reference declaration block exactly as follows:

```text
REFERENCE INPUTS:
[filename.jpg] = {placeholder_name}
References define physical details only — face, body, costume, structure, proportions.
Do NOT copy the rendering style or art style from the references.
Render all panels as cinematic photorealistic — as if shot on 35mm film
with a real camera, real skin, real fabric, real light.
Not illustration, not digital painting, not 2D, not CGI render.
```
- **Line 1:** Map the filename to its descriptive placeholder (e.g., `image1.jpg = {warrior_armor}`).
- **Subsequent lines:** Apply the global constraints and style override.
- **Specific roles:** If references serve distinct purposes, add concise roles:
  `{warrior_armor} defines the battle robe being removed.`

### Strict Rules (Avoid Overriding)
- **No Material Redundancy:** Do not describe materials already depicted in the reference (e.g., do not write "bamboo walls" when the reference clearly shows stone walls).
- **No Environmental Redundancy:** Do not describe environments already depicted in the reference (e.g., do not write "dark jungle" when the reference clearly shows a river bank).
- **No Attire/Feature Redundancy:** Do not repeat character features (face, hair, attire) unless they change state relative to the reference (e.g., write "battle robe removed" only if the reference is wearing it).

### Referencing Reference Images (Referencing Protocol)
If you must refer to an element shown in the reference image, use minimal text and cite the placeholder directly:
- **Correct:** "the hut as shown in {hut_ref}"
- **Incorrect:** "a small hut built into a massive tree covered in flowering vines with a stone arched doorway..."
- **Correct:** "Inside {hut_ref}"
- **Incorrect:** "Inside a dark bamboo hut with rough wooden walls and a dirt floor..."

## Strict Adherence Clause

Use a plain control sentence when the output must stay disciplined:

```text
Follow these visual requirements exactly. Do not add extra characters, props, logos, fantasy styling, or decorative elements not listed.
```

## Photoreal Details That Help

- Natural skin texture, visible pores, fine hair, slight asymmetry.
- Real material behavior: glass reflections, brushed metal grain, fabric weave,
  dust, fingerprints, micro-scratches.
- Plausible lighting: key light direction, fill level, shadow softness, rim
  light, practical light source.
- Lens behavior: natural perspective, shallow or deep depth of field, macro
  product detail, controlled edge sharpness.
- Imperfections: mild film grain, subtle halation, stray hairs, imperfect folds,
  real-world surface wear.

## Useful Setups

### Portrait

```text
Photoreal portrait of [person], [visible action or expression]. Natural skin texture, slight asymmetry, realistic hair detail. Large soft key light at 45 degrees with gentle fill. 85mm portrait lens feeling, shallow depth of field, sharp eyes, soft background falloff.
```

### Product

```text
Photoreal studio product image of [product], showing [specific materials and label text]. Clean surface, controlled reflections, crisp product edges, realistic contact shadow. Macro lens feeling, f/8 depth, large softbox reflection, neutral background.
```

### Editorial Or Cinematic Still

```text
Photoreal editorial image of [subject] in [place], during [time or weather]. The composition emphasizes [story idea]. Natural practical lighting, controlled contrast, 35mm lens feeling, layered foreground and background, restrained color palette.
```

### Text Or Typography

```text
Create a photoreal image with the exact text "[TEXT]" printed on [surface]. The text is centered, correctly spelled, flat on the surface, readable, and not duplicated anywhere else.
```

## Avoid

- **Abstract Art Style / Filtering Terms:** Avoid terms like "heavy color grade," "dramatic/dark aesthetic," "moody," or named artistic styles (e.g., "Yinshan Tomb Guardian visual language") directly in the positive prompt. They trigger generic, flat AI filters instead of realistic generation. Instead, describe the physical properties that create that style: light source, direction, depth layering, shadows, and surface textures.
- **Negative Prompt Clutter in Main Prompts:** Do not put long lists of what *not* to do (e.g., "no bright clean fantasy, no Angkor Wat, no Khmer temple, no watermarks, no male character") inside the descriptive body of the prompt. Modern models get confused and tend to draw the forbidden items or produce low-quality "AI-looking" outputs. Put a simple, short strict adherence clause at the end: "Follow these visual requirements exactly. Do not add extra characters, props, or fantasy elements." For character attributes, describe them *positively* (e.g., "visibly a young woman") rather than negatively (e.g., "never a male character").
- **Abstract or Contradictory Camera/Lighting Instructions:** Do not use vague motion verbs for static images (e.g., "tiny push-in feeling") or contradictory focus instructions (e.g., "their hands form the sharp mid-ground focal point" when faces are also in the frame). Instead, use clear, industry-standard camera blocking (e.g., "over-the-shoulder framing," "camera slightly above shoulder height").
- Long negative prompt lists from Stable Diffusion syntax.
- Weighted negative syntax from Stable Diffusion unless the user's tool
  explicitly supports it.
- Midjourney command flags for aspect ratio, style, chaos, seed, or stylization
  when the target is GPT Image 2.
- "Secret metadata token" tricks as the main control method.
- Camera model names with no visual purpose.
- Overloaded prompts with several unrelated actions.
