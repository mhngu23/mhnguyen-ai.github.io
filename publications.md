---
layout: page
title: Publications
permalink: /publications/
---


## 2026

- **ICML 2026**  
  *Reviving Error Correction in Modern Deep Time-Series Forecasting*  
  **Authors**: **Minh Hoang Nguyen**, Huu Hiep Nguyen, Dung Nguyen, Kien Do, Hung Le

- **AISTATS 2026**  
  *Spectral Text Fusion: A Frequency-Aware Approach to Multimodal Time-Series Forecasting*  
  **Authors**: Huu Hiep Nguyen, **Minh Hoang Nguyen**, Dung Nguyen, Hung Le

## 2025

- **ICDM 2025**  
  *[Accelerating Long-Term Molecular Dynamics with Physics-Informed Time-Series Forecasting](https://arxiv.org/pdf/2510.01206?)*  
  **Authors**: Hung Le, Sherif Abbas, **Minh Hoang Nguyen**, Van Dai Do, Huu Hiep Nguyen, Dung Nguyen  
  <details>
  <summary>Abstract</summary>
  Efficient molecular dynamics (MD) simulation is vital for understanding atomic-scale processes in materials science and biophysics. Traditional density functional theory (DFT) methods are computationally expensive, which limits the feasibility of long-term simulations. We propose a novel approach that formulates MD simulation as a time-series forecasting problem, enabling advanced forecasting models to predict atomic trajectories via displacements rather than absolute positions. We incorporate a physics-informed loss and inference mechanism based on DFT-parametrised pair-wise Morse potential functions that penalize unphysical atomic proximity to enforce physical plausibility. Our method consistently surpasses standard baselines in simulation accuracy across diverse materials. The results highlight the importance of incorporating physics knowledge to enhance the reliability and precision of atomic trajectory forecasting. Remarkably, it enables stable modeling of thousands of MD steps in minutes, offering a scalable alternative to costly DFT simulations.
  </details>

- **ECAI 2025**  
  *[Cross-Domain Offline Reinforcement Learning with Nearest-Neighbor Guided Diffusion Model](https://arxiv.org/pdf/2507.20499?)*  
  **Authors**: Linh Le Pham Van, **Minh Hoang Nguyen**, Duc Kieu, Hung Le, Hung The Tran, Sunil Gupta  
  <details>
  <summary>Abstract</summary>
  Cross-domain offline reinforcement learning (RL) seeks to enhance sample efficiency in offline RL by utilizing additional offline source datasets. We address challenges arising from limited target data, particularly dataset imbalance and partial domain overlap. We propose DmC, which uses k-nearest neighbor estimation to measure domain proximity without neural network training, and introduces a nearest-neighbor-guided diffusion model to generate better-aligned source samples. Our approach outperforms existing methods in MuJoCo environments.
  </details>

- **ECML/PKDD 2025**  
  *[Hybrid Cross-domain Robust Reinforcement Learning](https://arxiv.org/pdf/2505.23003?)*  
  **Authors**: Linh Le Pham Van, **Minh Hoang Nguyen**, Hung Le, Hung Tran The, Sunil Gupta  
  <details>
  <summary>Abstract</summary>
  Robust reinforcement learning (RL) aims to learn policies that remain effective despite uncertainties in its environment, which frequently arise in real-world applications due to variations in environment dynamics. We introduce HYDRO, a hybrid framework combining offline datasets with online simulator data for robust RL. HYDRO uses uncertainty filtering and prioritized sampling to select the most relevant and reliable simulator samples, measuring performance gaps between simulated and worst-case models to improve sample efficiency in offline robust RL training.
  </details>

- **IJCAI 2025**  
  *[Beyond the Known: Decision Making with Counterfactual Reasoning Decision Transformer](https://arxiv.org/pdf/2505.09114)*  
  **Authors**: **Minh Hoang Nguyen**, Linh Le Pham Van, Thommen George Karimpanal, Sunil Gupta, Hung Le  
  <details>
  <summary>Abstract</summary>
  Decision Transformers (DT) play a crucial role in modern reinforcement learning, leveraging offline datasets to achieve impressive results across various domains. However, DT requires high-quality, comprehensive data to perform optimally. We introduce the Counterfactual Reasoning Decision Transformer (CRDT), which generates counterfactual experiences to improve decision-making in unfamiliar scenarios. Testing on Atari and D4RL benchmarks demonstrates that CRDT surpasses conventional Decision Transformer approaches, particularly with restricted datasets and modified environments. A notable capability is trajectory stitching — combining suboptimal paths without requiring architectural changes — highlighting how counterfactual reasoning enhances generalization in reinforcement learning agents.
  </details>

## 2024

- **ECML/PKDD 2024**  
  *[Variable-Agnostic Causal Exploration for Reinforcement Learning](https://doi.org/10.1007/978-3-031-70344-7_13)*  
  **Authors**: **Minh Hoang Nguyen**, Hung Le, Svetha Venkatesh  
  <details>
  <summary>Abstract</summary>
  Modern reinforcement learning (RL) struggles to capture real-world cause-and-effect dynamics, leading to inefficient exploration due to extensive trial-and-error actions. We present VACERL, a framework that leverages causal relationships to improve agent exploration without requiring predefined environmental variables. The approach uses attention mechanisms to identify critical observation-action sequences, then builds a causal graph to guide agents toward pairs with greater causal impact on task success. This framework can generate intrinsic rewards or establish subgoal hierarchies to boost exploration efficiency, demonstrating improvements across grid-worlds, 2D games, and robotic tasks — particularly in sparse-reward and noisy-action scenarios.
  </details>

- **AAMAS 2024 Tutorial**  
  *[Reinforcement Learning Exploration via Memory](https://github.com/rl-memory-exploration-tutorial/rl-memory-exploration-tutorial.github.io)*  
  **Authors**: Hung Le, **Minh Hoang Nguyen**, Van Dai Do

## 2023

- **ACM SAC 2023**  
  *[Rug-pull Malicious Token Detection on Blockchain Using Supervised Learning with Feature Engineering](https://doi.org/10.1145/3579375.3579385)*  
  **Authors**: **Minh Hoang Nguyen**, Phuong Duy Huynh, Son Hoang Dau, Xiaodong Li
