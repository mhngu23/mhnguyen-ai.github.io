---
title: "CausalPlan: Causal Structure for LLM Multi-Agent Planning"
summary: "Learning what actually enables what in a task, then using that structure to steer an LLM agent's decisions — no fine-tuning required."
paper: https://arxiv.org/pdf/2508.13721
---

Large language models can describe a task beautifully and still act incoherently: reaching
for an onion with both hands full, serving soup that hasn't finished cooking, or duplicating
what a partner is already doing. CausalPlan fixes this at the point of decision. We learn a
compact **Structural Causal Action (SCA) model** from gameplay — a graph of which states and
prior actions genuinely enable each next action — and use it to rescore the LLM's proposals
as they are generated.

The language model keeps doing what it is good at, proposing sensible options; the causal
structure decides which of those options the world will actually accept. No fine-tuning, no
prompt surgery, and it drops onto any black-box LLM.

## What you see

Two Overcooked episodes under identical conditions — same kitchen, same seed, same partner,
same Llama-3-8B backbone. The only difference is CausalPlan.

- **Left** — the LLM's proposals rescored by the learned causal action matrix.
- **Right** — the same LLM, planning on its own.

The left panel shows each decision as it happens: every action proposed, how often it was
proposed, and the action finally
chosen. The moments marked ⚡ are causal structure overruling a confident but ill-timed
suggestion.

<figure>
  <video class="demo-video" controls preload="metadata">
    <source src="{{ '/assets/videos/causalplan_demo.mp4' | relative_url }}" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>CausalPlan (left) against the unaided LLM (right) &mdash; same kitchen, same model, same partner.</figcaption>
</figure>

In this episode the CausalPlan agent scores **60 to the baseline's 40**, idles on `wait` for
12% of the clock rather than 49%, and is steered **56 times** — continuous live correction,
not a one-off. At step 121 the LLM's most confident proposal was `pickup(dish)`, suggested in
9 of 20 samples; CausalPlan found `pickup(onion)` better supported by the current kitchen
state (2.29 vs 2.11) and chose it instead.

## Results

Across LLM backbones, causal rescoring is worth up to **+29% task reward** (Qwen-14B +29.0%,
Llama-70B +22.4%). It beats specialised RL coordination agents — SP, PBT, FCP, MEP, COLE — on
three of five layouts, with a 39% margin over the strongest baseline on Asymmetric Advantages,
and gains ~30% over ProAgent and COLE when partnered with human-proxy agents. Invalid pickups
fall 18%, valid interactions rise 17%, and actions that conflict with a partner disappear
entirely. A graph learned in one kitchen keeps about 94% of its benefit when reused in another.
