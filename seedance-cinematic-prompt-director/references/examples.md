# Seedance Prompt Examples

Worked examples showing input and full output.

## Example 1: Action Scene From Vague Request

### User Input

> ฉากเผชิญหน้าในตรอกกลางคืน สองคนปะทะกัน ดูดิบๆ จริงๆ

### Output

**Duration:** 8 seconds

**Scene:** A narrow wet alley at night. Two men confront each other at close
range. The encounter is raw and exhausting, not choreographed.

**Character A:** Male, late 20s, wearing a dark gray hoodie pulled back off his
head, exposing short black hair. Jeans and scuffed white sneakers. Left sleeve
is torn at the shoulder seam. Sweat visible on forehead.

**Character B:** Male, early 30s, wearing a wrinkled black t-shirt and cargo
pants. Heavier build. A smudge of dirt across his right cheekbone. Breathing
hard.

**Action:** Character A shoves Character B against the alley wall with both
hands. B absorbs the impact with his shoulder, then grabs A's hoodie collar and
pulls him off-balance. A stumbles forward into the wall. B pins him there for a
moment. A twists free and pushes B back. Both separate by a step, hands up,
breathing hard. Neither commits to another move.

**Performance:** No martial arts. The movements are short-range and sloppy. Both
men are tired — movements are heavy, not fast. Breathing is audible. A winces
when his shoulder hits the wall. B shakes out his gripping hand — it cramped
from the grab.

**Camera:** Handheld medium shot, eye level. The camera is close — roughly 2
meters from the confrontation. Slight handheld shake increases during impact
moments. The camera does not circle or crane. It stays planted like a third
person standing in the alley, watching.

**Lighting/Color:** A single sodium vapor streetlight at the far end of the
alley casts orange-amber light. The near end is darker. Wet ground reflects the
light in broken streaks. Faces are partially lit — key light from the left, deep
shadow on the right. Desaturated palette except for the warm orange light.

**Sound:** Scuffling shoes on wet ground. The hoodie fabric stretching during
the grab. The dull thud of a body against brick. Heavy breathing echoing off the
alley walls.

**Continuity:** Both characters maintain their clothing damage throughout. The
dirt on B's face was there before this shot — it is not fresh. The wet ground is
consistent. Screen direction: A enters from frame left, B is pushed frame right
toward the wall.

**Final Seedance Prompt:**

```text
An 8-second handheld medium shot in a narrow wet alley at night. Two men confront each other at close range. A young man in a torn dark gray hoodie shoves a heavier man in a black t-shirt against the brick wall. The heavier man absorbs the impact, grabs the hoodie collar, and pulls him off-balance. The young man stumbles into the wall. He twists free and pushes back. Both separate by a step, hands raised, breathing hard, exhausted. The confrontation is raw and scrappy — no martial arts, no acrobatics. A sodium vapor streetlight at the end of the alley casts orange light on wet ground. Faces are half-lit, half in shadow. The camera shakes slightly on impact. Wet footstep sounds and a dull thud of body against brick echo in the alley.
```

---

## Example 2: Multi-Shot Storyboard Sequence

### User Input

> I need a 3-shot Seedance sequence: a woman discovers her apartment has been
> broken into. Build tension, don't show the intruder.

### Output

**Character:** Woman, mid-30s, wearing a navy blue wool coat over a white
blouse, carrying a brown leather shoulder bag. Dark hair tied back in a low
ponytail. She looks tired — coming home from work.

**Continuity anchors:** Navy coat, brown bag, low ponytail, apartment key on a
simple metal ring. The apartment has a dark green front door, hardwood floors,
warm table lamp lighting. Time: evening.

| Shot | Duration | Beat                             | Camera                                  | Continuity From Previous                      | Final Prompt |
| ---- | -------: | -------------------------------- | --------------------------------------- | --------------------------------------------- | ------------ |
| 1    |       6s | Arrival — something is wrong     | Static medium shot                      | Sequence start                                | See below    |
| 2    |       5s | Discovery — door is open         | Slow push in, handheld                  | She was reaching for the keyhole              | See below    |
| 3    |       8s | Entry — the violation is visible | Following behind her, over-the-shoulder | She pushed the door open at the end of shot 2 | See below    |

**Shot 1 — Arrival**

```text
A 6-second static medium shot in an apartment hallway. A woman in a navy blue wool coat carrying a brown leather shoulder bag walks toward a dark green apartment door at the end of a dimly lit corridor. Warm overhead hallway light. Her footsteps echo on tile floor. She reaches into her bag for keys, pulls out a key ring, and approaches the door. As she reaches toward the lock, her hand slows — she notices something. Her body stiffens slightly. She tilts her head. The camera does not move. Quiet hallway ambience, her footsteps, the jingle of the key ring stopping.
```

**Shot 2 — Discovery**

```text
A 5-second close-up with a slow handheld push in. The dark green apartment door is open by three inches — the lock plate is damaged, wood splintered around the bolt. The woman's hand with the key ring enters frame from the right side and freezes near the damaged lock. Her fingers tighten around the keys. She does not touch the door yet. The camera pushes in slowly from the lock damage to her hand. Shallow depth of field — the crack of darkness through the open door is visible but blurred. The only sound is her breathing and a faint ambient hum from inside the apartment.
```

**Shot 3 — Entry**

```text
An 8-second over-the-shoulder handheld shot following behind the woman as she pushes the dark green door open with her fingertips and steps into her apartment. The camera stays behind her, showing what she sees: a warm table lamp is on, but drawers are pulled open, papers are scattered on the hardwood floor, a bookshelf has been partially emptied. Her brown shoulder bag slides off her arm and drops to the floor — she doesn't pick it up. She stands still in the doorway, one hand on the door frame. The camera slowly drifts to the right to reveal more of the ransacked room past her shoulder. No intruder visible. Evening light through a window mixes with the table lamp glow. The only sound is the ambient room tone and the soft thud of the dropped bag.
```

**Sequence logic:** Shot size narrows the audience's focus (medium → close-up →
over-the-shoulder reveals). Camera shifts from static observation to intimate
following. Sound strips away until only breathing and silence remain. The
intruder is never shown — the evidence is enough.

---

## Example 3: Fixing An Overloaded Prompt

### User Input

> My Seedance prompt: "An epic cinematic masterpiece shot of a beautiful warrior
> princess in ornate golden armor riding a magnificent white stallion through a
> burning medieval village while villagers flee in terror and dramatic
> orchestral music swells as she raises her legendary glowing sword toward a
> massive dragon descending from stormy skies with lightning, 4K HDR
> ultra-realistic." What's wrong with this?

### Output

**Problems:**

1. **Too many actions in one clip.** Riding, burning village, fleeing villagers,
   raising sword, dragon descending, lightning — this is a full movie trailer
   compressed into one shot. Seedance produces short clips (4-15 seconds). One
   clip cannot hold all of this.
2. **Vague style words.** "Epic cinematic masterpiece," "magnificent,"
   "legendary glowing" — none of these are visual instructions.
3. **No camera.** Where is the camera? What shot size? What movement?
4. **No performance specifics.** "Beautiful warrior princess" is a costume, not
   a character. What is she doing with her body?
5. **Copyrighted risk.** "Warrior princess" + "golden armor" + "white stallion"
   may drift toward existing IP. Describe original traits.
6. **"4K HDR ultra-realistic"** — resolution tags do not change the output.

**Fix: Split into 3 focused shots.**

**Shot 1 — The Ride Through Fire (6 seconds)**

```text
A 6-second tracking shot at horse-riding speed. A woman in dented bronze plate armor rides a gray horse at a gallop through a dirt road between burning wooden buildings. Embers drift across the frame. She leans forward in the saddle, jaw set, left hand gripping the reins, right hand holding a straight sword flat against the horse's neck. Her dark braided hair streams behind her. The camera tracks alongside at the same speed, medium shot, slightly below eye level. Firelight from both sides casts moving orange light on the armor. Smoke drifts across the lens. Sound of hooves on dirt, crackling fire, and the horse breathing hard.
```

**Shot 2 — Villagers (4 seconds)**

```text
A 4-second wide shot from a low angle at the edge of the village road. Three villagers — a man carrying a child, an older woman with a bundle — run toward the camera and past it, frame left to frame right. Behind them, the armored woman on the gray horse gallops through the background, smaller in frame, partially obscured by smoke. The camera is static. Firelight from a burning roof illuminates the villagers' faces. The sound is dominated by running footsteps, a child crying, and distant fire.
```

**Shot 3 — The Stand (8 seconds)**

```text
An 8-second low-angle shot. The woman in bronze armor pulls the gray horse to a stop at the village edge and looks up. She raises the sword overhead with both hands — the blade catches orange firelight. Her face is lit from below by ground fire and from above by cold gray storm light breaking through clouds. The horse shifts nervously beneath her. Wind pulls at her braid and the horse's mane. The camera is low and static, looking up at her against the dark sky. A large shadow passes over her from above — something overhead, unseen, blocking the light for a moment. She does not flinch. Thunder rumbles. No dragon is shown — only its shadow and the wind displacement.
```

**What changed:** One impossible shot became three filmable clips. The dragon is
implied, not rendered (reducing artifact risk). The character is original
(bronze armor, gray horse, braided dark hair — not a known IP). Every shot has
one clear action, a specific camera, and concrete performance.
