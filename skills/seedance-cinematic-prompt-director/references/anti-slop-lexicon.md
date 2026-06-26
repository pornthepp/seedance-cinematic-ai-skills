# Anti-Slop Lexicon

Replace empty evaluation language with observable production language. Field-confirmed across prompting communities in every supported language: abstract quality words destabilize generation because the model cannot tell which element to emphasize; decomposing them into physical elements (camera verb + speed + viewpoint, light source + direction + behavior, material + texture + motion) stabilizes it.

## The Six Slop Classes

| Class | Looks like | Repair |
|---|---|---|
| Empty evaluators | `cinematic, epic, stunning, beautiful, dramatic` | convert each to the one observable detail that earns it |
| Borrowed image-model tokens | `8K, masterpiece, award-winning, trending on ArtStation, Unreal Engine, RAW` | delete; resolution and quality are settings or outcomes, never prose |
| Tag salad | comma-separated keyword dumps ported from image prompting | rewrite as shooting-brief prose: one sentence per element — subject, action, camera, light, sound |
| Negation slop | `no blur, no artifacts, no distortion, no extra fingers` | negation summons; exclude compositionally — describe what IS there instead |
| Adjective stacking | `gorgeous, breathtaking, mesmerizing sunset` | three synonyms make one weak claim; pick the single detail that matters |
| Feel-suffix words | `電影感 · 雰囲気のある · 감성적인 · atmosférico · атмосферный · vibey` | name the physical cause of the feeling; every vocab file has a language-specific Slop Traps table |

## Replacement Table

| Weak phrase | Replace with |
|---|---|
| cinematic | shot scale, camera move, lighting, grade |
| epic | physical scale, stakes, crowd size, lens distance |
| beautiful | color, texture, composition, material, light behavior |
| stunning / breathtaking | visible contrast, reveal, movement, or detail |
| dynamic | specific movement, speed, and endpoint |
| dramatic | blocking, shadow, silence, or camera pressure |
| ultra-realistic | material behavior, skin pore, fabric weave, light falloff, lens distortion |
| masterpiece / 8K | delete — these are settings, not prose |
| moody | low-key ratio, practicals only, fog/haze density, desaturated palette |
| vibrant | name the hue, saturation context, and contrast pair |
| ethereal | overexposure amount, diffusion level, backlight, floaty motion speed |
| intense | close framing, shallow DOF, fast dolly, or silence before the beat |

## How to Apply

1. Write the full prompt draft.
2. Search for every adjective and adverb.
3. For each, ask: "What physical element earns this word?"
4. Replace the adjective with that element.
5. If no physical element exists, the word is decoration — cut it.
