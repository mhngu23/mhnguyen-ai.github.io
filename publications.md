---
layout: page
title: Publications
permalink: /publications/
---

## 📚 Peer-Reviewed Publications

### 2026

- **ICML 2026**  
  *[Reviving Error Correction in Modern Deep Time-Series Forecasting](https://arxiv.org/pdf/2605.21088)*  
  **Authors**: **Minh Hoang Nguyen**, Dai Do, Huu Hiep Nguyen, Dung Nguyen, Kien Do, Hung Le  
  <details>
  <summary>Abstract</summary>
  Modern deep-learning models have achieved remarkable success in time-series forecasting. Yet, their performance degrades in long-term prediction due to error accumulation in autoregressive inference, where predictions are recursively used as inputs. While classical error correction mechanisms (ECMs) have long been used in statistical methods, their applicability to deep learning models remains limited or ineffective. In this work, we revisit the error accumulation problem in deep time-series forecasting and investigate the role and necessity of ECMs in this new context. We propose a simple, architecture-agnostic error correction model that can be integrated with any existing forecaster without requiring retraining. By explicitly decomposing predictions into trend and seasonal components and training the corrector to adjust each separately, we introduce the Universal Error Corrector with Seasonal-Trend Decomposition (UEC-STD), which significantly improves correction accuracy and robustness across 4 backbones and 10 datasets. Our findings provide a practical tool for enhancing forecasts while offering new insights into mitigating autoregressive errors in deep time-series models.
  </details>

- **AISTATS 2026**  
  *[Spectral Text Fusion: A Frequency-Aware Approach to Multimodal Time-Series Forecasting](https://arxiv.org/pdf/2602.01588)*  
  **Authors**: Huu Hiep Nguyen, **Minh Hoang Nguyen**, Dung Nguyen, Hung Le  
  <details>
  <summary>Abstract</summary>
  Multimodal time series forecasting is crucial in real-world applications, where decisions depend on both numerical data and contextual signals. The core challenge is to effectively combine temporal numerical patterns with the context embedded in other modalities, such as text. While most existing methods align textual features with time-series patterns one step at a time, they neglect the multiscale temporal influences of contextual information such as time-series cycles and dynamic shifts. This mismatch between local alignment and global textual context can be addressed by spectral decomposition, which separates time series into frequency components capturing both short-term changes and long-term trends. In this paper, we propose SpecTF, a simple yet effective framework that integrates the effect of textual data on time series in the frequency domain. Our method extracts textual embeddings, projects them into the frequency domain, and fuses them with the time series' spectral components using a lightweight cross-attention mechanism. This adaptively reweights frequency bands based on textual relevance before mapping the results back to the temporal domain for predictions. Experimental results demonstrate that SpecTF significantly outperforms state-of-the-art models across diverse multi-modal time series datasets while utilizing considerably fewer parameters.
  </details>

### 2025

- **ICDM 2025**  
  *[Accelerating Long-Term Molecular Dynamics with Physics-Informed Time-Series Forecasting](https://arxiv.org/pdf/2510.01206)*  
  **Authors**: Hung Le, Sherif Abbas, **Minh Hoang Nguyen**, Van Dai Do, Huu Hiep Nguyen, Dung Nguyen  
  <details>
  <summary>Abstract</summary>
  Efficient molecular dynamics (MD) simulation is vital for understanding atomic-scale processes in materials science and biophysics. Traditional density functional theory (DFT) methods are computationally expensive, which limits the feasibility of long-term simulations. We propose a novel approach that formulates MD simulation as a time-series forecasting problem, enabling advanced forecasting models to predict atomic trajectories via displacements rather than absolute positions. We incorporate a physics-informed loss and inference mechanism based on DFT-parametrised pair-wise Morse potential functions that penalize unphysical atomic proximity to enforce physical plausibility. Our method consistently surpasses standard baselines in simulation accuracy across diverse materials. The results highlight the importance of incorporating physics knowledge to enhance the reliability and precision of atomic trajectory forecasting. Remarkably, it enables stable modeling of thousands of MD steps in minutes, offering a scalable alternative to costly DFT simulations.
  </details>

- **ECAI 2025**  
  *[Cross-Domain Offline Reinforcement Learning with Nearest-Neighbor Guided Diffusion Model](https://arxiv.org/pdf/2507.20499)*  
  **Authors**: Linh Le Pham Van, **Minh Hoang Nguyen**, Duc Kieu, Hung Le, Hung The Tran, Sunil Gupta  
  <details>
  <summary>Abstract</summary>
  Cross-domain offline reinforcement learning (RL) seeks to enhance sample efficiency in offline RL by utilizing additional offline source datasets. We address challenges arising from limited target data, particularly dataset imbalance and partial domain overlap. We propose DmC, which uses k-nearest neighbor estimation to measure domain proximity without neural network training, and introduces a nearest-neighbor-guided diffusion model to generate better-aligned source samples. Our approach outperforms existing methods in MuJoCo environments.
  </details>

- **ECML/PKDD 2025**  
  *[Hybrid Cross-domain Robust Reinforcement Learning](https://arxiv.org/pdf/2505.23003)*  
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

### 2024

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

### 2023

- **ACSW 2023 (ACM)**  
  *[Rug-pull Malicious Token Detection on Blockchain Using Supervised Learning with Feature Engineering](https://doi.org/10.1145/3579375.3579385)*  
  **Authors**: **Minh Hoang Nguyen**, Phuong Duy Huynh, Son Hoang Dau, Xiaodong Li  
  <details>
  <summary>Abstract</summary>
  Rug-pull scams, in which token creators abruptly withdraw liquidity and abandon a project, are one of the most damaging forms of fraud on decentralised exchanges. This work investigates the detection of rug-pull tokens on Uniswap using supervised learning. We aggregate a set of 23 candidate features characterising token contracts, liquidity, and transaction behaviour, and propose a hybrid feature-selection technique to identify the subset most predictive of rug-pull activity. Trained on this refined feature set, our classifier attains an F1-score of 99% and a precision of 97% on non-malicious tokens, demonstrating that careful feature engineering enables accurate, practical screening of malicious tokens on-chain.
  </details>

---

## 📄 Preprints

<p class="preprint-note">Under review / not yet peer-reviewed.</p>

- **arXiv 2026 · 2607.24892**  
  *[LLM as Forecasting Planner: Training-Free Text Conditioning for Time-Series Foundation Models](https://arxiv.org/pdf/2607.24892)*  
  **Authors**: Huu Hiep Nguyen, Dung Nguyen, **Minh Hoang Nguyen**, Dai Do, Hung Le  
  <details>
  <summary>Abstract</summary>
  Text-conditioned time-series forecasting predicts a series from both its numerical history and natural-language context, allowing forecasts to account for events and constraints that the past alone cannot reveal. This requires both reliable numerical forecasting and the ability to interpret contextual information. Time-series foundation models (TSFMs) provide strong numerical forecasts, while large language models (LLMs) can reason over text, but combining their strengths remains challenging because asking an LLM to generate or revise forecast values directly can distort the temporal structure captured by the TSFM. We instead formulate forecasting as a planning problem over TSFM-generated trajectories. The frozen TSFM acts as a simulator that proposes numerical continuations, while the LLM acts as a policy and value function that guides candidate selection and evaluates completed trajectories against the context. We instantiate this as LAFP (LLM As Forecasting Planner), a training-free framework that bridges the modality gap without retraining either model, using Monte Carlo tree search (MCTS) over the forecast horizon with a Ranker LLM as policy and a Judge LLM as value function. Experiments on Context-is-Key and Time-MMD across two TSFM backbones (Chronos and TimesFM) and four LLMs show that it delivers consistent improvements across model choices, supporting sequential search as an effective training-free approach to text-conditioned forecasting.
  </details>

- **arXiv 2026 · 2607.19659**  
  *[Expert-Guided Forecast Editing for Time-Series Foundation Models](https://arxiv.org/pdf/2607.19659)*  
  **Authors**: Hung Le, **Minh Hoang Nguyen**, Manh Nguyen, Huu Hiep Nguyen, Dai Do  
  <details>
  <summary>Abstract</summary>
  Time-series foundation models can forecast across heterogeneous domains without task-specific training, but their forecasts are fixed once produced and cannot directly incorporate task-specific expert feedback. We study expert-guided forecast editing: a frozen foundation model generates candidate future trajectories, and an expensive expert evaluator scores them to guide forecast revision. Under a tight query budget, two natural strategies sit at opposite ends: best-of-N purely exploits the foundation model's predictive distribution, while optimization approaches mostly explore the forecast horizon as an unstructured high-dimensional vector. Each extreme is individually sub-optimal. We introduce DEFT, an expert-guided forecast editing framework that balances the two by first exploiting the foundation model's predictive samples in a decomposed trend-seasonal space, then exploring around them via component-wise refinement. DEFT queries the expert only on complete trajectories, then reuses scores for the trend and seasonal components that appeared in the queried recombinations. This lets each expert query provide structured component-level feedback while keeping the foundation model frozen. We compare DEFT against direct search approaches, including best-of-N, cross-entropy methods, and Bayesian optimization, under matched expert-query budgets. Across two forecasting benchmarks consisting of 78 datasets, three time-series foundation models, four feedback types, and seven query budgets, DEFT consistently improves the effectiveness of expert guidance. A molecular-dynamics case study further suggests that the same principle extends to more physically grounded feedback, supporting the hypothesis that sparse test-time guidance should be spent balancing prior exploitation with structured exploration.
  </details>

- **arXiv 2026 · 2606.25800**  
  *[ROAD-VLA: Robust Online Adaptation via Self-Distillation for Vision-Language-Action Models](https://arxiv.org/pdf/2606.25800)*  
  **Authors**: Kejing Wang, Toan Nguyen, **Minh Hoang Nguyen**, Simon Khan, Flora D. Salim  
  <details>
  <summary>Abstract</summary>
  Effective online adaptation of vision-language-action (VLA) models remains challenging, as sparse rewards provide weak supervision for high-dimensional autoregressive action policies. Although self-distillation can in principle provide denser training signals, we find that text-based privileged teachers conditioned on demonstrations, retrieved experiences, or high-level plans are ineffective for VLA adaptation, exposing a modality gap between symbolic guidance and low-level robot actions. We propose ROAD-VLA, an advantage-guided self-distillation framework that constructs a proximal teacher directly in action space by perturbing action-token logits with calibrated advantage estimates. This converts sparse rewards into dense token-level supervision while keeping the teacher close to the current policy. We further derive a policy-improvement lower bound under calibrated advantages and accurate teacher matching. Across seven robotic manipulation environments with in-distribution and out-of-distribution shifts, ROAD-VLA outperforms PPO in nearly all settings, demonstrating robust online VLA adaptation.
  </details>

- **arXiv 2026 · 2606.19413**  
  *[Does Text Actually Help? Uncovering and Resolving Text Collapse in Multimodal Time Series Forecasting](https://arxiv.org/pdf/2606.19413)*  
  **Authors**: Huu Hiep Nguyen, **Minh Hoang Nguyen**, Dung Nguyen, Hung Le  
  <details>
  <summary>Abstract</summary>
  Multimodal time series forecasting, which pairs numerical sequences with domain-relevant textual reports, promises to inject world knowledge into forecasting pipelines. However, we uncover a critical failure mode in existing frameworks that we term text collapse: the text branch converges to a content-independent transformation, contributing negligible discriminative signal regardless of the input description. We argue that text collapse is a consequence of a fundamental asymmetry in time series forecasting: the numerical input is strongly autocorrelated with the output, making the numerical backbone inherently dominant, while the text branch, despite carrying complementary and often critical information, is insufficiently utilized, leading to its systematic underexploitation. To address this, we propose REST-TS (Residual-Exclusive Supervision for Text in Time Series), which turns the asymmetry into a design principle: the numerical backbone produces its own independent numerical forecast, and the text branch is exclusively supervised to predict the structured components of the residual, the prediction gap that numbers cannot explain. Because no numerical pathway can reduce these losses, the text branch must extract genuine content from the input description. Evaluated across diverse real-world domains and backbone architectures, REST-TS achieves state-of-the-art performance and consistently demonstrates greater text-branch utilization than existing frameworks, providing strong empirical evidence that supervising the text branch on the residual compels it to extract genuine content from the input.
  </details>

- **arXiv 2026 · 2606.19412**  
  *[Spectral Retrieval-Augmented Time-Series Forecasting](https://arxiv.org/pdf/2606.19412)*  
  **Authors**: Huu Hiep Nguyen, **Minh Hoang Nguyen**, Dung Nguyen, Hung Le  
  <details>
  <summary>Abstract</summary>
  Time series forecasting leverages historical patterns to predict future values, but traditional methods face challenges when dealing with complex, non-stationary patterns that are difficult to memorize during training. Retrieval-augmented approaches have emerged as promising solutions by retrieving similar historical patterns to enhance predictions. However, existing retrieval methods suffer from two fundamental limitations: spectral blindness, which overlooks critical frequency-domain characteristics that capture underlying periodic structures, and temporal recency, which treats all historical data equally without emphasizing recent, more relevant patterns. In this paper, we propose SpecReTF, a novel retrieval method that addresses these issues by converting time series into windowed frequency representations, measuring similarity with a combined metric that captures both amplitude and phase information. To balance recency and historical context, we apply an exponential moving average weighting scheme that emphasizes recent windows. Extensive experiments on benchmark datasets demonstrate that SpecReTF outperforms time-domain retrieval methods, achieving superior forecasting accuracy across diverse, non-stationary time series.
  </details>

- **arXiv 2025 · 2508.13721**  
  *[CausalPlan: Empowering Efficient LLM Multi-Agent Collaboration Through Causality-Driven Planning](https://arxiv.org/pdf/2508.13721)*  
  **Authors**: **Minh Hoang Nguyen**, Van Dai Do, Dung Nguyen, Thin Nguyen, Hung Le  
  <details>
  <summary>Abstract</summary>
  Large language model (LLM) agents - especially smaller, open-source models - often produce causally invalid or incoherent actions in collaborative tasks due to their reliance on surface-level correlations rather than grounded causal reasoning. This limitation undermines their performance in terms of coordination and planning in dynamic environments. We address this challenge with CausalPlan, a two-phase framework that integrates explicit structural causal reasoning into the LLM planning process. At the core of CausalPlan is the Structural Causal Action (SCA) model, which learns a causal graph from agent trajectories to capture how prior actions and current environment states influence future decisions. This structure is then used to guide action selection by assigning causal scores to LLM-generated proposals, reweighting them accordingly, or falling back to causally grounded alternatives when needed. By embedding this causal knowledge directly into the decision loop, CausalPlan constrains planning to intervention-consistent behaviours without requiring fine-tuning of the LLM itself. We evaluate CausalPlan on the Overcooked-AI benchmark across five multi-agent coordination tasks and four LLMs of varying sizes: Gemma-7B, Llama-8B, Qwen-14B, and Llama-70B. Experimental results show that CausalPlan consistently reduces invalid actions and improves collaboration in both AI-AI and human-AI settings, outperforming strong reinforcement learning baselines. Our findings highlight the value of causality-driven planning for deploying efficient, interpretable, and generalisable multi-agent LLM systems.
  </details>
