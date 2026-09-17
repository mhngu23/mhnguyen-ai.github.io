---
title: "Teaching a Language Model to Write Better Reward Functions"
summary: "Evolving the prompt that guides reward authoring, scored by the performance of the robots it produces — entirely on open-weight models."
---

Writing the reward function is the hard part of reinforcement learning. You describe what
you want in English, someone turns it into a scalar the agent maximises, and if the
translation is subtly wrong the robot learns something absurd instead. A language model can
do that translation. The question here is whether the *instructions given to that model* can
be improved automatically, using the resulting robot as the measure.

GEPA proposes edits to the reward-authoring prompt. Each candidate is scored by actually
training robots with the rewards it writes — a code judge measures the trajectory, a vision
model watches the rollout. Better prompts survive. Everything runs on one A100 with
Qwen3-VL-8B-Instruct in every role: reward author, judge, video critic, and the reflection
step that proposes the edits. No proprietary models.

<figure>
  <img src="{{ '/assets/images/prompt2policy-pipeline.png' | relative_url }}"
       alt="One session: a task in English, the model writes a reward, PPO trains a policy, two judges score it, and GEPA rewrites the prompt from that feedback." />
</figure>

## HalfCheetah, run forward

The task, as given to the model in English:

> *“Run forward at a steady moderate speed without flipping over.”*

<div class="video-pair">
  <figure>
    <video class="demo-video" controls preload="metadata" muted loop>
      <source src="{{ '/assets/videos/prompt2policy/cheetah-forward-stock.mp4' | relative_url }}" type="video/mp4">
    </video>
    <figcaption>Stock prompt &mdash; 0.50</figcaption>
  </figure>
  <figure>
    <video class="demo-video" controls preload="metadata" muted loop>
      <source src="{{ '/assets/videos/prompt2policy/cheetah-forward-evolved.mp4' | relative_url }}" type="video/mp4">
    </video>
    <figcaption>Evolved prompt &mdash; 0.83</figcaption>
  </figure>
</div>

Nine candidate prompts, four accepted, 150 training sessions. On the backward-running task
the evolved prompt reached a perfect 1.00 — but the more interesting number is the average:
the stock prompt managed 0.69 across its sessions, so what evolution bought there was
reliability rather than a higher ceiling.

## Humanoid, walk upright

> *“Walk forward keeping the torso perfectly upright with zero tilt.”*

A 3D biped with 17 actuated joints and a 348-dimensional observation. Unlike the cheetah,
it can fall over — and mostly does.

<div class="video-pair">
  <figure>
    <video class="demo-video" controls preload="metadata" muted loop>
      <source src="{{ '/assets/videos/prompt2policy/humanoid-stock.mp4' | relative_url }}" type="video/mp4">
    </video>
    <figcaption>Stock prompt &mdash; 68 steps upright</figcaption>
  </figure>
  <figure>
    <video class="demo-video" controls preload="metadata" muted loop>
      <source src="{{ '/assets/videos/prompt2policy/humanoid-evolved.mp4' | relative_url }}" type="video/mp4">
    </video>
    <figcaption>Evolved prompt &mdash; 123 steps upright</figcaption>
  </figure>
</div>

The score more than doubles (0.064 → 0.147) and the robot stays upright roughly twice as
long, walking forward at 0.56 m/s. Two edits did the real work.

**Stop guessing observation indices.** The environment reports forward speed both at index
22 of a 348-element vector and by name in the info dictionary. Under the original prompt the
8B model kept miscounting — writing `obs[25]` (torso roll rate) or `obs[23]` (sideways
drift) and confidently commenting that this was forward velocity. Those policies were being
paid to spin, and collapsed within a second. The evolved prompt says it plainly: *read
`info['x_velocity']`, do not derive velocity from an observation index.*

**Weight posture above speed.** The prompt grew a section on scale dominance, warning that
any term much larger than the rest causes the policy to ignore everything else. Applied to a
biped, it produced a ten-to-one ratio favouring staying upright over moving:

```python
r_upright = 10.0 * (1 - (pitch**2 + roll**2))     # posture dominates
r_forward = 1.0  * info.get('x_velocity', 0.0)    # speed, read by name
r_ctrl    = 0.05 * np.sum(action**2)              # effort penalty
```

A humanoid that chases velocity first simply falls over.

## The budget, not the reward

Each session trains for 1 million steps — a tenth of the standard budget for this
environment. Given the full budget, the same family of reward walks six metres before
falling:

<figure>
  <video class="demo-video" controls preload="metadata" muted loop>
    <source src="{{ '/assets/videos/prompt2policy/humanoid-3m.mp4' | relative_url }}" type="video/mp4">
  </video>
  <figcaption>Same reward family, 3M steps instead of 1M.</figcaption>
</figure>

So the humanoid result is budget-limited rather than reward-limited. The signal that matters
is the one upstream: a small open-weight model, given a prompt that its own robots' failures
helped write, produces reward functions that work — where a third of its earlier attempts
produced nothing usable at all.
