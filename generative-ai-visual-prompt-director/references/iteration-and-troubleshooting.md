# Iteration And Troubleshooting

Iteration is controlled diagnosis, not adjective accumulation. Preserve a
working baseline, change one variable, and compare against a named visual goal.

## Minimum Iteration Loop

1. Name the most important failure in one sentence.
2. Classify it: identity, composition, action, light, material, style, text, or
   temporal continuity.
3. Keep the successful parts unchanged.
4. Change one prompt block, reference, or control.
5. Generate a small comparison set.
6. Record what improved, regressed, and stayed uncertain.
7. Keep the change only if it improves the named goal.

When supported, hold the reproducibility state fixed while diagnosing. Release
it when exploring alternatives.

## Diagnose Before Rewriting

| Symptom | Likely cause | First test |
| --- | --- | --- |
| Subject identity drifts | Weak or competing identity anchors | Reduce decorative detail; repeat only stable visible traits and test one identity reference |
| Composition is ignored | Subject, environment, and camera compete | Move framing and spatial relationship earlier; remove secondary action |
| Image looks generic | Mood words lack visible evidence | Replace adjectives with light source, materials, weather, gesture, and production details |
| Too many objects appear | Loose lists imply equal importance | Name one hero subject and assign each supporting object a location or function |
| Hands or prop contact fail | Interaction is physically ambiguous | Simplify the pose; describe which hand, grip, contact point, and visible angle |
| Text is malformed | Exact typography exceeds the system's reliable capability | Generate clean space or a sign surface; add final text in a separate design step |
| Reference overwhelms the scene | Influence is too broad or purpose is unclear | Assign the reference one role only: identity, pose, composition, palette, or motion |
| Style overwhelms meaning | Style cues outnumber story cues | Restore subject, action, and composition; keep one coherent style family |
| Video warps or morphs | Too much simultaneous change | Shorten duration; use one action, one camera move, and a defined ending state |
| Camera motion feels random | Movement has no dramatic verb | State what the camera does, its speed, and why the beat needs that movement |
| Shot-to-shot continuity breaks | Anchors were not carried forward | Repeat identity, wardrobe, prop state, screen direction, light, and emotional handoff |

## Rewrite By Layer

Do not replace the entire prompt at once. Edit the smallest responsible layer:

- **Identity:** age range, silhouette, face cues, hair, wardrobe, signature prop
- **Action:** one visible verb, pose, contact point, direction
- **Space:** foreground, subject plane, background, relative positions
- **Camera:** shot size, height, angle, lens feeling, movement
- **Light:** source, direction, hardness, color relationship, exposure priority
- **Surface:** material, wear, moisture, texture scale, reflection behavior
- **Story:** emotion shown through posture, gaze, distance, or environment
- **Continuity:** immutable anchors and permitted changes

## Exclusions And Negative Instructions

Use exclusions only for a recurring, visible failure. Write the positive target
first, then add a short exclusion. Do not use a long exclusion list to compensate
for an unclear subject or composition.

## Escalation Rules

- After two failed wording changes, test whether the system supports the needed
  capability.
- After identity or pose keeps drifting, introduce a purpose-specific reference
  if supported.
- After exact text keeps failing, move typography to a deterministic design step.
- After complex motion keeps failing, split the beat into shorter shots.
- If a requirement conflicts with another requirement, ask the user to rank
  them instead of pretending both can be guaranteed.

## Comparison Log

```text
Goal:
Baseline:
Failure class:
Variable changed:
What stayed fixed:
Result:
Regression:
Decision: keep / revert / test again
Next smallest test:
```

## Stop Conditions

Stop iterating when the primary visual goal is met, remaining defects do not
change meaning or delivery, and another change risks a known success. Report any
remaining limitation plainly.
