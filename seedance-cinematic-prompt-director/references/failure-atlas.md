# Failure Atlas

Use this reference when output fails. Match the symptom to its likely cause
and apply the primary repair.

## Generation Failures

| Symptom | Likely cause | Primary repair |
|---|---|---|
| Continuation begins from planned ending, not actual | Parent observed state was not reviewed | Replace opening with observed end state |
| Action restarts from beginning | Completed beat was not marked as done | Add completed beat exclusion |
| Future event appears early | Reserved beat leaked into prompt | Remove future beat from prompt and endpoint |
| Identity drifts through extensions | Continuity source displaced canonical identity | Re-anchor identity from canonical image reference |
| Screen direction flips | Axis was not locked or reset intentionally | State screen direction explicitly or declare axis change |
| Style flickers between shots | Sampler hopping between nearby clusters | Repeat exact style anchor phrase in every shot |
| Subject frozen / no motion | Prompt described state, not action | Add one physical verb with endpoint |
| Glitchy emotion / instant expression | Emotion was rushed, no time to land | Give the key beat at least 2 seconds |
| Extra limbs or fingers | Dense action + close framing | Reduce action complexity or widen framing |
| Text/watermark appears | No exclusion constraint | Add `no on-screen text, no watermark` constraint |
| Audio desyncs from video | Competing rhythm sources | Mute video ref; let audio ref control timing |
| Camera move ignored | Fast tier or too many simultaneous instructions | Use Standard tier; simplify to one camera move |

## Sequence Failures

| Symptom | Likely cause | Primary repair |
|---|---|---|
| Shot 2 ignores Shot 1 style | No style anchor repeated | Copy exact style phrase across all shots |
| Multi-shot renders as one take | Missing Shot N: labels | Add explicit Shot 1: / Shot 2: labels |
| Beats compressed or skipped | Duration too short for shot count | Increase to 10–15s or use `auto` |
| Character looks different across shots | No identity reference locked | Assign [Image1] as identity source in every shot |
