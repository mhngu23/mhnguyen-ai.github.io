---
title: "From Egocentric Video to Robot Demonstrations"
summary: "Turning ordinary head-mounted-camera footage of a person doing a task into the same task performed by a robot, in the same real scene."
tags: [Robotics, Vision-Language-Action, Egocentric Video]
---

We turn ordinary egocentric video of a person doing a task into the same task performed
by a robot, in the same real scene. Starting from a head-mounted camera recording, the
human hands are identified and removed, the scene's geometry is recovered, and a robot
arm is placed into the reconstructed scene so that it reproduces the original motion.

The result is robot demonstration footage grounded in real environments and real human
behaviour, rather than in simulation.

## What you see

Each clip steps through the same five views:

1. **Original** — the raw egocentric recording.
2. **Hand isolation** — the human hands picked out from the rest of the frame.
3. **Clean plate** — the same scene with the hands removed.
4. **Scene geometry** — the recovered three-dimensional structure of the environment.
5. **Robot** — a robot arm placed into that scene, reproducing the original motion.

## Desk tidying

<figure>
  <video class="demo-video" controls preload="metadata">
    <source src="{{ '/assets/videos/demo_declutter_desk_xarm7_allegro.mp4' | relative_url }}" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Desk tidying &mdash; xArm7 with an Allegro hand, 32s.</figcaption>
</figure>

## Cooking

<figure>
  <video class="demo-video" controls preload="metadata">
    <source src="{{ '/assets/videos/demo_boil_serve_egg_panda.mp4' | relative_url }}" type="video/mp4">
    Your browser does not support the video tag.
  </video>
  <figcaption>Boiling and serving an egg &mdash; Franka Panda, 31s.</figcaption>
</figure>

## Why it matters

Robot learning is bottlenecked by demonstration data. Teleoperating a real arm is slow
and expensive; simulation is cheap but carries a domain gap that policies have to cross.
Egocentric video sidesteps both — people already record a great deal of it, doing
ordinary tasks in ordinary places. Recasting that footage as robot demonstrations keeps
the diversity and physical realism of the real world while producing data in a form a
robot policy can actually learn from.
