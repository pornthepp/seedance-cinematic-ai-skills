# Event Density

Use this reference to decide how much story belongs in one generation.

## Density Rule

One generation should normally carry one visible beat with a changed
endpoint. Long backstory, multiple locations, multiple major actions,
dense dialogue, and future resolution belong in the sequence plan,
not the current prompt.

## Beat Buckets

Before writing any prompt in a sequence, classify every story beat:

| Bucket | Rule | Example |
|---|---|---|
| `already_happened` | Do not replay. Reference as context only. | "she already opened the door" |
| `this_clip_only` | The current prompt may perform this. | "she steps inside and pauses" |
| `reserved_for_later` | Do not show yet. Do not hint. | "she will discover the letter in shot 3" |
| `do_not_show_yet` | Excluded even if it explains motivation. | "her anger comes from a betrayal we haven't revealed" |

## Scope Firewall

Story context that motivates the current beat but is not visible in
this clip stays out of the prompt. The model cannot render motivation,
backstory, or future plans — only physical action in the present moment.

## When to Split

Split into multiple clips when:
- The beat has more than one major physical action
- The scene changes location
- More than 2 characters need simultaneous complex action
- Dialogue exceeds 3 speaker turns
- The emotional arc needs more than 15 seconds to land

## When to Combine

Keep in one clip when:
- The action is simple and continuous (walk, turn, sit)
- The emotional change is subtle (a glance, a pause)
- The camera move is motivated and carries the whole beat
