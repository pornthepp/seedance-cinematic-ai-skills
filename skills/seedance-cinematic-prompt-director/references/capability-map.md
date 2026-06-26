# Capability Map — Design Into Strengths, Around Limits

What Seedance 2.0 does best and what to design around. Load before prompt
planning.

## Design INTO These

| Capability | How to extract it |
|---|---|
| Multi-shot in one call | `Shot 1:/2:/3:` labels · one action + one camera each · Standard tier · 10–15s or `auto` |
| Native synced audio | name specific sounds; dialogue as quoted lines; short lines; clean front face ref; SFX > music > dialogue |
| Role-separated references | per-asset role + exclusion ("motion only, no appearance") |
| Motion transfer via @Video | donor clip for choreography/camera rhythm + identity @Image |
| Audio-as-clock via @Audio | "cut on the beat of @Audio1; the turn lands on the drop" |
| First/last frame (FLF) | lock endpoints; prompt initiate→travel→resolve; good for transformations & match-cuts |
| Literal camera verbs | one motivated move per shot: pan, tilt, dolly, push-in, pull-out, orbit |
| Physics | physical verbs & consequences, not pose adjectives |
| Slow motion | Standard tier; apply to the single key action only |
| Transformation | endpoint states + the persisting carrier; hard cases → FLF decomposition |
| 2D/Anime | medium grammar: cel over painted bg, sakuga vs held frames, impact frames/speed lines |
| Formats & `auto` | 21:9 for cinema; `auto` sizes duration to complexity |

## Design AROUND These

| Limitation | Workaround |
|---|---|
| Negation summons concepts | describe what IS there instead |
| Fast tier drops complexity | use Standard for multi-shot, slow-mo, complex camera |
| Identity drift in long clips | keep clips short; re-anchor from ORIGINAL references |
| Chained generation degrades | reset to original refs every 4–5 chains |
| Multiple simultaneous actions | one primary action per shot |
| Long non-English dialogue | keep lines very short; plan post-dub for long pieces |
| Dense hand/face + fast action | reduce action complexity OR split into clips |
| Style flicker between shots | repeat exact anchor phrase across shots |
| Unmotivated sudden changes | provide physical cause for every state change |
