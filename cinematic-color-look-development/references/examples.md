# Color Look Development Examples

Worked examples showing input and full output.

## Example 1: Building A Palette From Story

### User Input

> My short film is about a nurse who works night shifts. She's burning out but
> can't stop because her family depends on her. I need a color palette.

### Output

**Emotional color intention:** Exhaustion disguised as duty. The color should
feel like fluorescent light has drained the warmth out of everything — but small
moments of real warmth (home, her daughter) survive underneath.

**Palette logic:** Arc-based. The world starts cold and institutional, with
warmth appearing only in protected moments. As burnout deepens, even the warm
spaces start losing their color.

**Dominant palette:**

| Color                        | Hex Reference | Where                                         | Story Function                                      |
| ---------------------------- | ------------- | --------------------------------------------- | --------------------------------------------------- |
| Cool fluorescent green-white | `#E8F0E4`     | Hospital corridors, break room, nurse station | The institutional world that eats her time          |
| Pale blue-gray               | `#B8C4CC`     | Her scrubs, the bus ride, early morning sky   | Fatigue — the color of being between sleep and work |
| Dark teal                    | `#2A4A4E`     | Night exterior, parking lot, bus stop         | Isolation — the hours no one else is awake          |

**Accent colors:**

| Color       | Hex Reference | Where                                                         | Story Function                                   |
| ----------- | ------------- | ------------------------------------------------------------- | ------------------------------------------------ |
| Warm amber  | `#D4915A`     | Kitchen lamp at home, daughter's nightlight, a thermos of tea | Real human warmth — rare and protected           |
| Pale yellow | `#F2E6C4`     | Morning light through apartment curtains                      | Hope that she almost doesn't have time to notice |

**Forbidden color:** Saturated red. No bright reds until the climax — when she
finally breaks down, a red ambulance light strobes across her face. The red
arrives when her controlled surface cracks.

**Transition:** In the final scene, the fluorescent green-white should shift
slightly warmer — `#EDE8DC` — as she makes a decision about her life. Not a
dramatic change. Just enough that the audience feels something has shifted
without naming it.

**Lighting logic:**

- Hospital: overhead fluorescents, flat, no shadows. This is a world with no
  hiding.
- Home: single practical lamp, warm, shadows present. This is the only place
  with depth.
- Bus/exterior: sodium vapor streetlights and blue ambient. She exists between
  the two worlds.

**Grade note:**

- Lift the blacks slightly in hospital scenes — no true black, just washed-out
  shadow. Exhaustion flattens contrast.
- Crush the blacks on night exteriors — she disappears into darkness between
  shifts.
- Home scenes get normal contrast with warm midtones. This is the only place
  that feels like a real image.

**Continuity risk:** Her scrubs are pale blue-gray. Make sure the hospital
fluorescent does not push them green — unless the story is at peak burnout. Test
with skin tone reference patches.

---

## Example 2: Correcting A "Teal And Orange" Request

### User Input

> I want a teal and orange color grade for my crime thriller. Make it look like
> Sicario.

### Output

**Before applying this palette, three questions:**

1. **Why teal and orange?** If the answer is "because it looks cool" or "because
   Sicario did it," the palette will feel borrowed, not motivated. Sicario used
   desaturated warm tones because the story takes place in desert borderland
   heat — the environment dictated the color.

2. **What is your environment?** If your thriller is set in a rainy northern
   city, teal-and-orange will fight the location. The color should grow from
   where the story lives.

3. **What does color need to do in your story?** Crime thrillers often need
   color to separate worlds — the protagonist's safe world vs. the criminal
   world, daytime legality vs. nighttime illegality.

**If you still want a warm/cool split, here is a motivated version:**

**Palette logic:** Dual-world. The protagonist's legal life is cool and
controlled. The criminal world is warm, seductive, and dangerous.

| World        | Dominant                                                       | Accent                                                         | Lighting                                                       |
| ------------ | -------------------------------------------------------------- | -------------------------------------------------------------- | -------------------------------------------------------------- |
| Legal/police | Desaturated blue-gray, cold white fluorescent                  | Small notes of blue from screens and police lights             | Flat overhead, institutional                                   |
| Criminal     | Deep amber, warm shadow, tobacco-stained interiors             | Dark red in small doses — taillights, a neon sign, a wound     | Practical lamps, underexposed, pools of warm light in darkness |
| Transition   | The two worlds bleed together as the protagonist crosses lines | Blue creeps into warm scenes; amber invades the police station | Mixed sources, confused color temperature                      |

**Grade approach:**

- Legal world: slightly lifted blacks, desaturated, cool white balance. Feels
  bureaucratic.
- Criminal world: crushed blacks, warm highlights, selective saturation on skin
  and practical lights. Feels alive but dangerous.
- Climax: both worlds collapse into one color temperature — monochrome warm or
  monochrome cool, depending on which world wins.

**Skin tone protection:** In the cool legal scenes, watch for blue-cast skin.
Add a skin isolation node in the grade. In the warm criminal scenes, avoid
pushing skin into orange — keep it warm but natural.

**What this is not:** This is not "add teal to shadows and orange to highlights
globally." That is a filter, not a look. A motivated split uses color to tell
the audience which world they are in and how it feels.

---

## Example 3: Color Script For A 5-Scene Short

### User Input

> I have a 5-scene short about a retired teacher who visits his old school one
> last time before it's demolished. Can you map the color across scenes?

### Output

**Core arc:** Nostalgia vs. irreversible loss. Color should move from warm
memory to cold present, with one moment where both coexist.

| Scene         | Setting                                                  | Palette                                          | Light                                                                 | Emotional State                         | Color Note                                                                                                                                                                                                      |
| ------------- | -------------------------------------------------------- | ------------------------------------------------ | --------------------------------------------------------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 — Arrival   | Exterior, school gate, overcast morning                  | Desaturated, flat gray-green                     | Diffused overcast, no shadows                                         | Numbness, hesitation                    | Everything is drained. No color tells us how to feel yet. The school looks like any abandoned building.                                                                                                         |
| 2 — Hallway   | Interior, empty corridor, dust in air                    | Pale amber emerging from gray                    | A shaft of sunlight through a window catches dust particles           | First flicker of memory                 | The amber is the first warm color in the film. It enters through light, not objects. The walls are still gray.                                                                                                  |
| 3 — Classroom | Interior, his old room, desks removed                    | Warm amber dominant, soft gold light             | Late morning sun through large windows, dust motes                    | Full immersion in memory                | This is peak warmth. The room glows. For a moment, the demolition does not exist. His face is lit with warm, flattering light.                                                                                  |
| 4 — Discovery | He finds a student's drawing on the wall, faded          | Warm amber starts to cool at the edges           | Sun moves behind a cloud. The light shifts from gold to neutral white | The present reasserts itself            | The warmth is retreating. The drawing is faded — its color is almost gone. He touches it and his hand is in cool light while the drawing retains a trace of warmth.                                             |
| 5 — Departure | Exterior, walks away, demolition equipment in background | Return to gray, but slightly warmer than scene 1 | Overcast but with a thin gold line at the horizon                     | Acceptance — loss and gratitude coexist | The gray is back but not identical to scene 1. A faint warmth remains — `#D8D2CA` instead of `#C8C8C8`. The audience should feel that he carries something with him, even though the building will not survive. |

**Forbidden color:** Bright blue. Blue skies or vivid blue objects would create
a hopeful reading that undercuts the loss. Keep the sky overcast throughout.

**Continuity risk:** Scene 3 (peak warmth) to Scene 4 (cooling) is the critical
transition. The shift should happen within the scene, not between scenes. The
sun moving behind a cloud is the motivated cause. Do not cut from warm to cold —
let the audience watch the warmth leave.
