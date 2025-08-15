

<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses MIT license.
-->
<div align="center">
<h1>Survey of Verifier Design Mechanisms for Test Time Scaling of LLMs</h1>
</div>


<p align="center">
  <img src="https://img.shields.io/badge/Contributors-3-red?style=for-the-badge" />
  <img src="https://img.shields.io/github/stars/Verifierstesttimescaling.github.io/Verifierstesttimescaling.github.io?style=for-the-badge&label=Stars&color=blue"/>
  <img src="https://img.shields.io/endpoint?url=https://Verifierstesttimescaling.github.io/arxiv_citations.json&style=for-the-badge&color=green"/>
</p>


Our repository, **Survey of Verifier Design Mechanisms for Test Time Scaling of LLMs**, gathers available papers on different approaches for design and training of verification mechanisms for test-time scaling. To the best of our knowledge no comprehensive survey  Unlike other repositories that categorize papers, we decompose each paper's contributions based on the taxonomy provided by [""]() facilitating easier understand and comparison for readers.


<div align="center">
  <img src="figs/Verifier.png" width="900"/>
  <p><b>Figure 1:</b> A Visual Map and Comparison.</p>
</div>

## 📢 News and Updates
- **[15/Aug/2025]** 📌 Our repository is created.

## 📘 Introduction
Test-time scaling (TTS) has emerged as a new frontier for scaling the performance of Large Language Models. In test-time scaling, by using more computational resources during inference, LLMs can improve their reasoning process and task performance. Several approaches have emerged for TTS such as distilling reasoning traces from another model or exploring the vast decoding search space by employing a verifier. Employing external verifiers or self-verification is crucial for test-time scaling, as they help guide the search process over large reasoning space. Verification for test-time scaling entails  mechanisms or scoring functions used to evaluate the quality or plausibility of different reasoning paths or solutions from the language model during inference, enabling efficient search or selection among them without access to ground-truth labels.  This paradigm commonly termed has emerged as a superior approach owing to parameter free scaling at inference time and high performance gains. The verifiers could be prompt-based, fine-tuned as a discriminative or generative model to verify process paths, outcomes or both. Despite their widespread adoption, there is no detailed collection, clear categorization and discussion of diverse verification approaches and their training mechanisms. In this survey, we cover the diverse approaches in the literature and present a unified view of verifier training, types and their utility in test-time scaling.

<div align="center">
  <img src="figs/Verifier-taxonomy.png" width="900"/>
  <p><b>Figure 2:</b> Taxonomy for Verification Design and Training mechanisms.</i>.</p>
</div>


## 🔍 Overview of Works
| <div style="width:300px">Method(PapersTitles)</div> |   | SFT   | RL     | STI | SEA | VER | AGG |        |        |
|<i><b>Scaling llm test-time compute optimally can be more effective than scaling model parameters.</b></i>, <a href="https://arxiv.org/abs/2408.03314" target="_blank"><img src="https://img.shields.io/badge/arXiv-2408.03314-red" alt="arXiv Badge"></a></li>|Parallel,<br>Sequential|✗|✗|✗|Beam,<br>LookAhead|Verifier|(Weighted) Best-of-N,<br>Stepwise Aggregation|Math|Pass@1,<br>FLOPsMatched Evaluation|
|<i><b>Multi-agent verification: Scaling test-time compute with goal verifiers</b></i><br>., <a href="https://arxiv.org/abs/2502.20379" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.20379-red" alt="arXiv Badge"></a></li>| Parallel | ✗ | ✗ | Self-Repetition | ✗ | Multiple-Agent<br>Verifiers | Best-of-N | Math,<br>Code,<br>General | BoN-MAV (Cons@k),<br>Pass@1 |
|<i><b>Evolving Deeper LLM Thinking</b></i><br>,  <a href="https://arxiv.org/abs/2501.09891" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.09891-red" alt="arXiv Badge"></a></li>| Sequential | ✗ | ✗ | Self-Refine | ✗ | Functional | ✗ | Open-Ended | Success Rate,<br>Token Cost |
| <i><b>Meta-reasoner: Dynamic guidance for optimized inference-time reasoning in large language models</b></i><br>, <a href="https://arxiv.org/abs/2502.19918" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.19918-red" alt="arXiv Badge"></a></li>| Sequential | ✗ | ✗ | CoT +<br>Self-Repetition | ✗ | Bandit | ✗ | Game,<br>Sci,<br>Math | Accuracy,<br>Token Cost |
| <i><b>START: Self-taught reasoner with tools</b></i><br>, <a href="https://arxiv.org/abs/2503.04625" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.04625-red" alt="arXiv Badge"></a></li>| Parallel,<br>Sequential | Rejection Sampling | ✗ | Hint-infer | ✗ | Tool | ✗ | Math,<br>Code | Pass@1 |
| <i><b>" Well, Keep Thinking": Enhancing LLM Reasoning with Adaptive Injection Decoding</b></i><br>,  <a href="https://arxiv.org/abs/2503.10167" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.10167-red" alt="arXiv Badge"></a></li>| Sequential | ✗ | ✗ | Adaptive Injection<br>Decoding | ✗ | ✗ | ✗ | Math,<br>Logical,<br>Commonsense | Accuracy |
| <i><b>Chain of draft: Thinking faster by writing less</b></i><br>, <a href="https://arxiv.org/abs/2502.18600" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.18600-red" alt="arXiv Badge"></a></li> | Sequential | ✗ | ✗ | Chain-of-Draft | ✗ | ✗ | ✗ | Math,<br>Symbolic,<br>Commonsense | Accuracy,<br>Latency,<br>Token Cost |
| <i><b>rStar-Math: Small LLMs Can Master Math Reasoning with Self-Evolved Deep Thinking</b></i><br>, <a href="https://arxiv.org/abs/2501.04519" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.04519-red" alt="arXiv Badge"></a></li> | Hybrid | imitation | ✗ | ✗ | MCTS | PRM | ✗ | Math | Pass@1 |
| <i><b>Can 1B LLM Surpass 405B LLM? Rethinking Compute-Optimal Test-Time Scaling</b></i><br>, <a href="https://arxiv.org/abs/2502.06703" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.06703-red" alt="arXiv Badge"></a></li> | Parallel,<br>Hybrid | ✗ | ✗ | ✗ | DVTS,<br>Beam Search | PRM | Best-of-N | Math | Pass@1,<br>Pass@k,<br>Majority,<br>FLOPS |
| <i><b>Tree of thoughts: Deliberate problem solving with large language models</b></i><br>, <a href="https://arxiv.org/abs/2305.10601" target="_blank"><img src="https://img.shields.io/badge/arXiv-2305.10601-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | Propose Prompt,<br>Self-Repetition | Tree Search | Self-Evaluate | ✗ | Game,<br>Open-Ended | Success Rate,<br>LLM-as-a-Judge |
| <i><b>Mindstar: Enhancing math reasoning in pre-trained llms at inference time</b></i><br>, <a href="https://arxiv.org/abs/2405.16265" target="_blank"><img src="https://img.shields.io/badge/arXiv-2405.16265-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | ✗ | LevinTS | PRM | ✗ | Math | Accuracy,<br>Token Cost |
| <i><b>Inference Scaling Laws: An Empirical Analysis of Compute-Optimal Inference for LLM Problem-Solving</b></i><br>, <a href="https://arxiv.org/abs/2408.00724" target="_blank"><img src="https://img.shields.io/badge/arXiv-2408.00724-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | ✗ | Reward Balanced<br>Search | RM | ✗ | Math | Test Error Rate,<br>FLOPs |
| <i><b>Reasoning-as-Logic-Units: Scaling Test-Time Reasoning in Large Language Models Through Logic Unit Alignment</b></i><br>, <a href="https://arxiv.org/abs/2502.07803" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.07803-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | Self-Refine | Control Flow Graph | Self-Evaluate | Prompt Synthesis | Math,<br>Code | Pass@1 |
| <i><b>PlanGEN: A Multi-Agent Framework for Generating Planning and Reasoning Trajectories for Complex Problem Solving</b></i><br>, <a href="https://arxiv.org/abs/2502.16111" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.16111-red" alt="arXiv Badge"></a></li>  | Parallel,<br>Hybrid | ✗ | ✗ | MoA | ✗ | Verification Agent | Selection Agent | Math,<br>General,<br>Finance | Accuracy,<br>F1 Score |
| <i><b>A Probabilistic Inference Approach to Inference-Time Scaling of LLMs using Particle-Based Monte Carlo Methods</b></i><br>, <a href="https://arxiv.org/abs/2502.01618" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.01618-red" alt="arXiv Badge"></a></li>  | Hybrid | ✗ | ✗ | ✗ | Particle-based<br>Monte Carlo | PRM + SSM | Particle Filtering | Math | Pass@1,<br>Budget vs. Accuracy |
| <i><b>Archon: An Architecture Search Framework for Inference-Time Techniques</b></i><br>, <a href="https://arxiv.org/abs/2409.15254" target="_blank"><img src="https://img.shields.io/badge/arXiv-2409.15254-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | MoA,<br>Self-Repetition | ✗ | Verification Agent,<br>Unit Testing (Ensemble) | Fusion | Math,<br>Code,<br>Open-Ended | Pass@1,<br>Win Rate |
| <i><b>Wider or deeper? scaling llm inference-time compute with adaptive branching tree search</b></i><br>, <a href="https://arxiv.org/abs/2503.04412" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.04412-red" alt="arXiv Badge"></a></li> | Hybrid | ✗ | ✗ | Mixture-of-Model | AB-MCTS-(M,A) | ✗ | ✗ | Code | Pass@1,<br>RMSLE,<br>ROC-AUC |
| <i><b>Thinking llms: General instruction following with thought generation</b></i><br>, <a href="https://arxiv.org/abs/2410.10630" target="_blank"><img src="https://img.shields.io/badge/arXiv-2410.10630-red" alt="arXiv Badge"></a></li> | Internal,<br>Parallel | ✗ | DPO | Think | ✗ | Judge Models | ✗ | Open-Ended | Win Rate |
| <i><b>Self-Evolved Preference Optimization for Enhancing Mathematical Reasoning in Small Language Models</b></i><br>, <a href="https://arxiv.org/abs/2503.04813" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.04813-red" alt="arXiv Badge"></a></li> | Internal,<br>Hybrid | ✗ | DPO | Diversity Generation | MCTS | Self-Reflect | ✗ | Math | Pass@1 |
| <i><b>MA-LoT: Multi-Agent Lean-based Long Chain-of-Thought Reasoning enhances Formal Theorem Proving</b></i><br>, <a href="https://arxiv.org/abs/2503.03205" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.03205-red" alt="arXiv Badge"></a></li> | Internal,<br>Sequential | imitation | ✗ | MoA | ✗ | Tool | ✗ | Math | Pass@k |
| <i><b>Offline Reinforcement Learning for LLM Multi-Step Reasoning</b></i><br>, <a href="https://arxiv.org/abs/2412.16145" target="_blank"><img src="https://img.shields.io/badge/arXiv-2412.16145-red" alt="arXiv Badge"></a></li> | Internal,<br>Sequential | ✗ | OREO | ✗ | Beam Search | Value Function | ✗ | Math,<br>Agent | Pass@1,<br>Success Rate |
| <i><b>DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning</b></i><br>, <a href="https://arxiv.org/abs/2501.12948" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.12948-red" alt="arXiv Badge"></a></li> | Internal | warmup,<br>GRPO,<br>Rule-Based | ✗ | ✗ | ✗ | ✗ | Math,<br>Code,<br>Sci | Pass@1,<br>cons@64,<br>Percentile,<br>Elo Rating,<br>Win Rate |
| <i><b>s1: Simple test-time scaling</b></i><br>, <a href="https://arxiv.org/abs/2501.19393" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.19393-red" alt="arXiv Badge"></a></li> | Internal | distillation | ✗ | Budget Forcing | ✗ | ✗ | ✗ | Math,<br>Sci | Pass@1,<br>Control,<br>Scaling |
| <i><b>O1 Replication Journey: A Strategic Progress Report -- Part 1</b></i><br>, <a href="https://arxiv.org/abs/2410.18982" target="_blank"><img src="https://img.shields.io/badge/arXiv-2410.18982-red" alt="arXiv Badge"></a></li> | Internal | imitation | ✗ | ✗ | Journey Learning | PRM,<br>Critique | Multi-Agents | Math | Accuracy |
| <i><b>From drafts to answers: Unlocking llm potential via aggregation fine-tuning</b></i><br>, <a href="https://arxiv.org/abs/2501.11877" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.11877-red" alt="arXiv Badge"></a></li> | Internal,<br>Parallel | imitation | ✗ | ✗ | ✗ | Fusion | ✗ | Math,<br>Open-Ended | Win Rate |
| <i><b>Towards System 2 Reasoning in LLMs: Learning How to Think With Meta Chain-of-Though</b></i><br>,  <a href="https://arxiv.org/abs/2501.04682" target="_blank"><img src="https://img.shields.io/badge/arXiv-2501.04682-red" alt="arXiv Badge"></a></li>| Internal,<br>Hybrid | imitation,<br>meta-RL | Think | MCTS,<br>A* | PRM | ✗ | Math,<br>Open-Ended | Win Rate |
| <i><b>ReasonFlux: Hierarchical LLM Reasoning via Scaling Thought Templates</b></i><br>, <a href="https://arxiv.org/abs/2502.06772" target="_blank"><img src="https://img.shields.io/badge/arXiv-2502.06772-red" alt="arXiv Badge"></a></li> | Internal,<br>Sequential | ✗ | PPO,<br>Trajectory | Thought Template Retrieve | ✗ | ✗ | Math | Pass@1 |
| <i><b>L1: Controlling how long a reasoning model thinks with reinforcement learning</b></i><br>, <a href="https://arxiv.org/abs/2503.04697" target="_blank"><img src="https://img.shields.io/badge/arXiv-2503.04697-red" alt="arXiv Badge"></a></li> | Internal | ✗ | GRPO,<br>Length-Penalty | ✗ | ✗ | ✗ | ✗ | Math | Pass@1,<br>Length Error |
| <i><b>Marco-o1: Towards Open Reasoning Models for Open-Ended Solutions</b></i><br>, <a href="https://arxiv.org/abs/2411.14405" target="_blank"><img src="https://img.shields.io/badge/arXiv-2411.14405-red" alt="arXiv Badge"></a></li> | Internal,<br>Hybrid | distillation,<br>imitation | ✗ | Reflection Prompt | MCTS | Self-Critic | ✗ | Math | Pass@1,<br>Pass@k |




</footer>

<!-- 
## Generative Verifiers

1. [Putting the Value Back in RL: Better Test-Time Scaling by
Unifying LLM Reasoners With Verifiers] (https://arxiv.org/pdf/2505.04842 ) -->
