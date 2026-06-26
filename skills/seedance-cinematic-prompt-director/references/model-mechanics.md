# Model Mechanics — How the Generator Thinks

A working mental model of why this skill's rules work, so you can derive
correct guidance for cases no rule covers. Built from public machine-learning
knowledge and public model cards.

## The Eight Mechanisms

### 1. Attention Is a Budget

Every word competes for a finite amount of conditioning influence. Words that
name something visible spend the budget on pixels; words that name an
evaluation ("stunning") spend it on nothing. Earlier clauses tend to win
more influence.

**Consequences:** word order is a priority ranking · slop is not just ugly,
it is expensive · short dense prompts beat long prose.
**Explains:** the anti-slop system, the one-action discipline, "put subject
and action first."

### 2. Generation Pulls Toward the Familiar

The model produces samples near its training distribution. Combinations it
has seen millions of times (golden hour + warm rim light) are cheap and
stable; rare combinations fight the prior and wobble.

**Consequences:** name dense visual clusters (film noir, cel animation,
phone footage), not judgments (beautiful) · expect instability for
statistically rare requests · style flicker between shots is the sampler
hopping between nearby clusters — repeat the exact anchor phrase to hold it.
**Explains:** style-safe descriptors, the medium-line repetition rule in 2D
work, the source-look lock.

### 3. There Is No NOT

Text conditioning moves probability toward every concept it mentions.
Negation is weak grammar wrapped around a strong activation: "no blood"
still summons the concept.

**Consequences:** describe what IS there; exclude compositionally · reserve
literal negation for the constraint slot platforms parse
(`no on-screen text, no watermark`).
**Explains:** negation slop, "negation summons" in the capability map.

### 4. Time Is a Trajectory Prior

The model strongly prefers motion that looks like real footage: smooth,
momentum-carrying, cause-and-effect. A described cause lets the model
compute plausible consequences; disconnected micro-instructions have no
trajectory to ride.

**Consequences:** one physical cause with visible consequences beats five
stage directions · unmotivated sudden changes get smoothed away or glitch ·
declared media change the prior — "hand-drawn 2D" legitimizes held frames
that photoreal footage would treat as freezing.
**Explains:** physics-forward prompting, the one-action discipline.

### 5. Errors Compound

Each frame is re-synthesized under the influence of its neighbors; tiny
identity errors accumulate across a clip, and feeding outputs back as inputs
amplifies them generation after generation.

**Consequences:** identity drifts with clip length and chained continuations
— re-anchor with the ORIGINAL references, never with outputs · keep fragile
anchors locked and clips short · expect the fifth chained generation to need
a reset.
**Explains:** the ~4–5 generation drift note, extension-degradation warnings.

### 6. The Sampler Is Stochastic

Same prompt + different seed = different sample from the same distribution.
Some prompts have a narrow distribution (stable), others wide (variable).

**Consequences:** if two re-rolls with the same prompt both fail the same
way, the prompt is the problem, not bad luck · dense specific prompts have
narrow distributions (more predictable).
**Explains:** the re-roll vs rewrite distinction in the retake protocol.

### 7. References Compete

Multiple reference inputs (image, video, audio) each claim conditioning
influence. Without explicit role assignment, they fight.

**Consequences:** assign exactly one primary role per reference · use
exclusion statements ("motion only, no appearance") · when references
conflict, mute the weaker one.
**Explains:** role-separated references, audio conflict repair.

### 8. Resolution and Duration Are Shared Resources

Higher resolution and longer duration both dilute per-frame detail budget.
More seconds mean each frame gets less compute.

**Consequences:** match resolution to the delivery need, not "bigger is
better" · long clips with complex action will simplify themselves · use
`auto` duration when unsure.
**Explains:** multi-shot budget, keep clips short for complex work.
