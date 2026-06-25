# GPT Image 2 Prompt Examples

Worked examples showing input and full output.

## Example 1: Product Photo Prompt

### User Input

> I need a GPT Image 2 prompt for a Thai craft coffee brand. The product is a
> 250g matte black bag with gold foil text "DOI CHANG" on it. Premium feel,
> clean studio look.

### Output

**Final prompt:**

```text
Photoreal studio product image of a 250-gram matte black coffee bag standing upright on a polished dark slate surface. The bag has a flat bottom gusset and a clean rectangular shape with no wrinkles. Gold foil text "DOI CHANG" is printed across the upper third of the bag in clean sans-serif capitals, correctly spelled, appearing once only. Below the brand name, smaller gold text reads "Single Origin Arabica." The bag surface has a soft matte texture that absorbs light with minimal reflection. A few whole roasted coffee beans are scattered naturally on the slate surface to the right of the bag — dark brown with visible center cracks and slight oil sheen. Lighting: large softbox from upper left at 45 degrees creating a gentle gradient across the bag surface. A secondary fill card from the right keeps shadow detail visible. The gold foil catches a subtle highlight from the key light. Background is a smooth medium gray gradient, darker at edges. Macro lens feeling, f/8 depth of field, sharp product edges, soft shadow falloff on the slate. Neutral color temperature. Realistic contact shadow under the bag — soft, not cut out. Follow these visual requirements exactly. Do not add extra props, logos, plants, cups, or decorative elements not listed.
```

**Risk notes:**

- Typography is the highest-risk element. "DOI CHANG" is short (two words) which
  helps reliability. Requesting it once with exact placement reduces duplication
  risk.
- Gold foil on matte black is a high-contrast combination that tends to render
  well.
- The strict adherence clause at the end prevents the model from adding unwanted
  props like coffee cups, leaves, or burlap textures.

**If text renders incorrectly on first attempt:**

Refinement prompt — change only the text instruction:

```text
Keep everything the same. Fix the text on the bag: the words "DOI CHANG" should appear exactly once in the upper third of the bag, in gold foil sans-serif capitals, correctly spelled with proper letter spacing. No other text should appear on the bag except "Single Origin Arabica" below it in smaller gold text.
```

---

## Example 2: Editorial Portrait With Mood

### User Input

> Thai boxer after a fight. Not glamorous — real, tired, human. For a magazine
> editorial.

### Output

**Final prompt:**

```text
Photoreal editorial portrait of a Thai male Muay Thai fighter, early 20s, sitting on a low wooden bench in a dimly lit gym corner after a fight. His hands are still wrapped in fraying cloth hand wraps, stained with sweat. He rests his forearms on his knees, head slightly bowed, looking down and to the left. His face shows real fatigue — sweat on forehead, slightly swollen left cheekbone, damp hair pressed flat. Skin has natural texture: visible pores, minor blemishes, sweat beads on the bridge of his nose. His body is lean, not exaggerated — natural athletic build with visible muscle definition but not bodybuilder proportions. He wears red satin shorts with a faded white waistband, slightly rumpled. A white towel hangs over his left shoulder, partially covering a traditional Sak Yant tattoo on his upper back.

Lighting: single warm practical light source from upper right — a bare incandescent bulb hanging from a cord, casting strong directional light with hard shadows. The left side of his face falls into shadow with minimal fill. The bulb creates a small, hot highlight on his wet skin. Background is dark — glimpse of a heavy bag chain, a water bottle on the floor, a pair of abandoned gloves. The gym is concrete and worn.

85mm lens feeling, wide aperture, shallow depth of field. Sharp focus on his eyes and hands, background falls soft. The composition places him frame left with negative space to the right — the empty bench beside him. Slight film grain. Muted color palette: warm amber from the bulb, cool blue-gray in the shadows. No smile, no fighting pose, no victory gesture. Follow these visual requirements exactly. Do not add audience, ring ropes, referee, or glamorous lighting not described.
```

**Risk notes:**

- Sak Yant tattoo is partially covered to reduce complexity — full tattoo
  rendering can introduce artifacts.
- Specifying "lean, not exaggerated" prevents the model from defaulting to
  hyper-muscular stereotypes.
- Hand wraps are a simpler hand state than bare fists or boxing gloves with
  lacing, reducing anatomy risk.
- The strict clause prevents the model from adding a victory context that would
  contradict the "tired, human" mood.

---

## Example 3: Fixing A Failed Image — Refinement Loop

### User Input

> I generated this image of a glass perfume bottle on a marble surface.
> Problems: the glass looks plastic, the reflection is wrong, and there's a
> weird second bottle appearing in the background. Here's my original prompt: "A
> luxury perfume bottle on marble. Beautiful lighting. Elegant."

### Output

**Diagnosis:**

| Issue               | Cause                                                                                                              | Fix                                                                                                                  |
| ------------------- | ------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- |
| Glass looks plastic | No refraction, caustic, or internal reflection described. The word "luxury" doesn't teach the model glass physics. | Describe glass behavior: transparency, refraction distortion, internal color, caustic light patterns on the surface. |
| Wrong reflection    | No reflection logic specified. The model guessed.                                                                  | Describe what the marble surface reflects and how — soft, stretched, partial.                                        |
| Ghost second bottle | Prompt was too vague, so the model filled negative space with a duplicate.                                         | Add strict adherence clause. Describe the background explicitly. Specify "one bottle only."                          |

**Revised prompt:**

```text
Photoreal studio image of a single glass perfume bottle centered on a white Carrara marble surface with soft gray veining. The bottle is rectangular with beveled edges, clear glass, approximately 12cm tall. The glass is transparent — you can see the pale gold liquid inside and the subtle refraction distortion it creates on the far edge of the bottle. Small caustic light patterns fall on the marble surface near the bottle base where light passes through the glass. The bottle cap is polished silver metal with a brushed texture on top.

The marble surface reflects a soft, stretched, partial image of the bottle — not a mirror copy, but a diffused shape with lost detail. The reflection fades within 15cm of the bottle base.

Lighting: large rectangular softbox directly above and slightly behind the bottle, creating a clean white reflection stripe down the front glass face. A smaller fill from lower left opens the shadow side. The marble surface has a gentle light gradient — brighter in the center, falling off at the edges. Background is smooth white, seamless with the surface. No other objects, no second bottle, no props. One bottle only.

90mm macro lens feeling, f/11 depth of field for front-to-back sharpness. Neutral color temperature with a slight warm bias from the gold liquid. Follow these visual requirements exactly. Do not add flowers, fabric, additional bottles, or decorative elements.
```

**What changed:** Every problem traced to missing physical description. "Luxury"
became material behavior. "Beautiful lighting" became a specific softbox
position. "Elegant" became composition and lens choice. The strict clause
prevents the ghost duplicate.
