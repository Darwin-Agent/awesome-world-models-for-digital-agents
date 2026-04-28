<p align="center">
  <img src="public/banner.png" alt="Digital Agents Meet World Models: A Survey" width="100%"/>
</p>

# Awesome World Models for Digital Agents

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![arXiv](https://img.shields.io/badge/arXiv-XXXX.XXXXX-b31b1b)](https://arxiv.org/abs/XXXX.XXXXX) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) <!-- omit in toc -->

This repository accompanies [**Digital Agents Meet World Models: A Survey**](https://arxiv.org/abs/XXXX.XXXXX), providing a taxonomy-aligned bibliography of cited works and representative systems across games, web & GUI, tool-use, and code domains. The survey introduces a unified agent-centric design space **W = (X, L, U)**, organized around what is modeled, how predictive capability is built, and how world models are used inside the agent loop.

Papers are grouped by domain and listed in reverse chronological order within each subsection to support literature navigation, comparison, and ongoing updates.

## Table of Contents <!-- omit in toc -->

- [Taxonomy Overview](#taxonomy-overview)
- [Games](#games)
- [Web \& GUI](#web--gui)
- [Tool Use](#tool-use)
- [Code](#code)
- [Benchmarks \& Environments](#benchmarks--environments)
- [Datasets](#datasets)
- [Related Surveys](#related-surveys)
- [Welcome to Contribute](#welcome-to-contribute)
- [Citation](#citation)

## Taxonomy Overview

The survey organizes world models for digital agents along a unified design space **W = (X, L, U)**:

| Dimension | Question | Key Choices |
|:----------|:---------|:------------|
| **X: Model Specification** | *What is modeled?* | State deltas, Full observations, Latent transitions, Auxiliary outcomes |
| **L: Learning & System Realization** | *How is it built?* | LLM-based, Visual generative, Latent dynamics, Code-based, Hybrid/modular |
| **U: Agent-Facing Role** | *How is it used?* | Decision-time planning, Training-time interaction, Predictive verification |

### Representative Methods Mapped to (X, L, U)

| Method | Domain | X: Prediction Target | L: Paradigm | U: Usage |
|:-------|:-------|:---------------------|:------------|:---------|
| MuZero | Game | Latent transition (reward/value/policy) | Latent dynamics | Planning (MCTS) |
| EfficientZero | Game | Latent transition (reward/value) | Latent dynamics | Planning, training |
| DreamerV3 | Game | Latent transition (state/reward) | Latent dynamics | Training (imagined rollouts) |
| IRIS | Game | Full observation (tokens) | Latent dynamics | Training (imagined trajectories) |
| Genie | Game | Full observation (video) | Visual-generative | Training (env. generation) |
| WMA | Web | State delta (web transition) | LLM-based | Planning (policy selection) |
| WebWM | Web | State delta (web dynamics) | Hybrid/modular | Training (env. generation) |
| WebWorld | Web | Full observation (web page) | LLM-based | Training, planning |
| DynaWeb | Web | Full observation (web page) | LLM-based | Training (model-based RL) |
| WebEvolver | Web | State delta (web state) | LLM-based | Training (co-evolution), planning |
| VAGEN | Web/GUI | Latent transition (belief) | VLM/RL-based | Training |
| R-WoM | GUI | State delta (UI change) | Hybrid/modular | Planning, verification |
| ViMo | GUI | Full observation (GUI image) | Visual-generative | Planning (action evaluation) |
| MobileDreamer | GUI | Full observation (GUI sketch) | LLM-based | Planning (action evaluation) |
| Code2World | GUI | Full observation (renderable code) | Code-based | Planning (simulation) |
| CUWM | GUI | State delta (UI change) | LLM-based | Planning (action search) |
| SafePred | GUI | Auxiliary outcome (risk) | LLM-based | Verification (guardrail) |
| Agent World Model | Tool-use | Full observation (tool state) | Code-based | Training (env. generation) |
| GTM | Tool-use | Full observation (tool output) | LLM-based | Training (tool simulation) |
| ToolRM | Tool-use | Auxiliary outcome (tool reward) | LLM-based | Verification |
| WorldCoder | Code | State delta (program dynamics) | Code-based | Planning |
| Code World Models | Code | State delta (program dynamics) | Code-based | Planning, verification |
| CWM | Code | State delta (execution trace) | LLM-based | Verification |
| SWE-World | Code | Auxiliary outcome (execution feedback) | LLM-based | Training, verification |

## Games

World models for game environments, including classical model-based RL, visual game generation, and text-interactive worlds.

### Latent Dynamics & Model-Based RL

+ [**DreamerV3**](https://arxiv.org/abs/2301.04104) (Nature, 2025) — RSSM + symlog loss; generalizes across 150+ diverse tasks. [![Stars](https://img.shields.io/github/stars/danijar/dreamerv3?style=flat&logo=github&color=181717)](https://github.com/danijar/dreamerv3)
+ [**DIAMOND**](https://arxiv.org/abs/2405.12399) (NeurIPS, 2024) — U-Net diffusion transition operator for Atari. [![Stars](https://img.shields.io/github/stars/eloialonso/diamond?style=flat&logo=github&color=181717)](https://github.com/eloialonso/diamond)
+ [**STORM**](https://arxiv.org/abs/2310.09615) (NeurIPS, 2023) — Stochastic Transformer + VAE world model. [![Stars](https://img.shields.io/github/stars/weipu-zhang/STORM?style=flat&logo=github&color=181717)](https://github.com/weipu-zhang/STORM)
+ [**IRIS**](https://arxiv.org/abs/2209.00588) (ICLR, 2023) — VQ-VAE + Transformer autoregressive world model. [![Stars](https://img.shields.io/github/stars/eloialonso/iris?style=flat&logo=github&color=181717)](https://github.com/eloialonso/iris)
+ [**EfficientZero**](https://arxiv.org/abs/2111.00210) (NeurIPS, 2021) — MuZero + self-supervised consistency; sample-efficient. [![Stars](https://img.shields.io/github/stars/YeWR/EfficientZero?style=flat&logo=github&color=181717)](https://github.com/YeWR/EfficientZero)
+ [**MuZero**](https://arxiv.org/abs/1911.08265) (Nature, 2020) — Value-aligned latent dynamics with MCTS; masters Go, chess, Atari.
+ [**Dreamer**](https://arxiv.org/abs/1912.01603) (ICLR, 2020) — Latent imagination via RSSM; multi-step backpropagation. [![Stars](https://img.shields.io/github/stars/danijar/dreamer?style=flat&logo=github&color=181717)](https://github.com/danijar/dreamer)
+ [**AlphaStar**](https://doi.org/10.1038/s41586-019-1724-z) (Nature, 2019) — Grandmaster-level StarCraft II via multi-agent RL.
+ [**PlaNet (RSSM)**](https://arxiv.org/abs/1811.04551) (ICML, 2019) — Learning latent dynamics for planning from pixels. [![Stars](https://img.shields.io/github/stars/google-research/planet?style=flat&logo=github&color=181717)](https://github.com/google-research/planet)
+ [**World Models**](https://arxiv.org/abs/1803.10122) (NeurIPS, 2018) — VAE + MDN-RNN; influential early architecture. [![Stars](https://img.shields.io/github/stars/hardmaru/WorldModelsExperiments?style=flat&logo=github&color=181717)](https://github.com/hardmaru/WorldModelsExperiments)
+ [**AlphaGo**](https://doi.org/10.1038/nature16961) (Nature, 2016) — Deep neural networks and tree search for Go.

### Visual Game Generation

+ [**Oasis**](https://oasis-model.github.io) (Decart, 2024) — Transformer-based real-time interactive world generation.
+ [**GameNGen**](https://arxiv.org/abs/2408.14837) (ICLR, 2025) — U-Net diffusion runs DOOM at 20 FPS.
+ [**Genie**](https://arxiv.org/abs/2402.15391) (ICML, 2024) — Latent action discovery; generative interactive environment from video.
+ [**The Matrix**](https://arxiv.org/abs/2412.03568) (arXiv, 2024) — Infinite-horizon world generation with real-time moving control.

### Text-Interactive Worlds

+ [**WALL-E 2.0**](https://arxiv.org/abs/2504.15785) (arXiv, 2025) — Neuro-symbolic world alignment for text-world planning. [![Stars](https://img.shields.io/github/stars/siyuzhou/WALL-E?style=flat&logo=github&color=181717)](https://github.com/siyuzhou/WALL-E)
+ [**From Word to World**](https://arxiv.org/abs/2512.18832) (arXiv, 2025) — Evaluating LLMs as implicit text-based world models.
+ [**Game-TARS**](https://arxiv.org/abs/2510.23691) (arXiv, 2025) — Pretrained foundation models for scalable generalist multimodal game agents.
+ [**WALL-E 1.0**](https://arxiv.org/abs/2410.07484) (arXiv, 2024) — Rule-aligned world model for LLM agents in text environments.
+ [**PlanCraft**](https://arxiv.org/abs/2412.21033) (arXiv, 2024) — Planning with LLM agents over structured crafting dependencies. [![Stars](https://img.shields.io/github/stars/gautierdag/plancraft?style=flat&logo=github&color=181717)](https://github.com/gautierdag/plancraft)
+ [**Mars**](https://arxiv.org/abs/2410.08126) (arXiv, 2024) — Situated inductive reasoning in an open-world environment.
+ [**RAFA**](https://arxiv.org/abs/2309.17382) (arXiv, 2023) — Principled planning framework for autonomous LLM agents.
+ [**RAP**](https://arxiv.org/abs/2305.14992) (EMNLP, 2023) — Reasoning with language model is planning with world model.
+ [**ReAct**](https://arxiv.org/abs/2210.03629) (ICLR, 2023) — Synergizing reasoning and acting with implicit world simulation.

### Implicit World Modeling & Reasoning

+ [**Neuro-Symbolic Synergy**](https://arxiv.org/abs/2602.10480) (arXiv, 2026) — Neuro-symbolic synergy for interactive world modeling.
+ [**Current Agents Fail to Leverage WM**](https://arxiv.org/abs/2601.03905) (arXiv, 2026) — Negative evidence on agents using world models as foresight tools.
+ [**General Agents Contain World Models**](https://arxiv.org/abs/2506.02996) (ICML, 2025) — Theoretical result on world models in general agents.
+ [**LAW**](https://arxiv.org/abs/2312.05230) (arXiv, 2023) — Language models, agent models, and world models framework.
+ [**Tree of Thoughts**](https://arxiv.org/abs/2305.10601) (NeurIPS, 2023) — Deliberate problem solving with implicit future simulation.
+ [**Reflexion**](https://arxiv.org/abs/2303.11366) (NeurIPS, 2023) — Language agents with verbal reinforcement learning.

## Web & GUI

World models for web navigation, desktop/mobile GUI interaction, and computer-use agents.

### Web Navigation

+ [**WAC**](https://arxiv.org/abs/2602.15384) (arXiv, 2026) — World-model-augmented web agents with action correction.
+ [**WebWorld**](https://arxiv.org/abs/2602.14721) (arXiv, 2026) — Large-scale LLM-based world model for web agent training.
+ [**DynaWeb**](https://arxiv.org/abs/2601.22149) (arXiv, 2026) — Model-based reinforcement learning of web agents.
+ [**WebSynthesis**](https://arxiv.org/abs/2507.04370) (arXiv, 2025) — World-model-guided MCTS for efficient web trajectory synthesis. [![Stars](https://img.shields.io/github/stars/LucusFigoGao/WebSynthesis?style=flat&logo=github&color=181717)](https://github.com/LucusFigoGao/WebSynthesis)
+ [**WebEvolver**](https://arxiv.org/abs/2504.21024) (arXiv, 2025) — Self-improvement with coevolving world model for web agents.
+ [**WebWM**](https://arxiv.org/abs/2512.23676) (arXiv, 2025) — Web World Models; semantic HTML delta prediction.
+ [**WebDreamer**](https://arxiv.org/abs/2411.06559) (TMLR, 2025) — LLM web state simulation + tree search for planning. [![Stars](https://img.shields.io/github/stars/OSU-NLP-Group/WebDreamer?style=flat&logo=github&color=181717)](https://github.com/OSU-NLP-Group/WebDreamer)
+ [**WMA Web Agent**](https://arxiv.org/abs/2410.13232) (ICLR, 2025) — Learning and leveraging environment dynamics in web navigation. [![Stars](https://img.shields.io/github/stars/kyle8581/WMA-Agents?style=flat&logo=github&color=181717)](https://github.com/kyle8581/WMA-Agents)

### GUI — Desktop & Computer-Use

+ [**Computer-Using World Model**](https://arxiv.org/abs/2602.17365) (arXiv, 2026) — LLM-based UI state delta prediction for action search.
+ [**SafePred**](https://arxiv.org/abs/2602.01725) (arXiv, 2026) — Predictive guardrail for computer-using agents via world models.
+ [**ActionEngine**](https://arxiv.org/abs/2602.20502) (arXiv, 2026) — State machine memory for programmatic GUI agents.
+ [**NeuralOS**](https://arxiv.org/abs/2507.08800) (arXiv, 2025) — RNN + pixel diffusion for desktop GUI simulation. [![Stars](https://img.shields.io/github/stars/yuntian-group/neural-os?style=flat&logo=github&color=181717)](https://github.com/yuntian-group/neural-os)
+ [**R-WoM**](https://arxiv.org/abs/2510.11892) (arXiv, 2025) — Retrieval-augmented world model for computer-use agents.

### GUI — Mobile

+ [**gWorld**](https://arxiv.org/abs/2602.01576) (arXiv, 2026) — VLM code rendering for mobile world simulation. [![Stars](https://img.shields.io/github/stars/trillion-labs/gWorld?style=flat&logo=github&color=181717)](https://github.com/trillion-labs/gWorld)
+ [**Code2World**](https://arxiv.org/abs/2602.09856) (arXiv, 2026) — GUI world model via renderable code generation. [![Stars](https://img.shields.io/github/stars/AMAP-ML/Code2World?style=flat&logo=github&color=181717)](https://github.com/AMAP-ML/Code2World)
+ [**MobileDreamer**](https://arxiv.org/abs/2601.04035) (arXiv, 2026) — Generative sketch world model for GUI agents.
+ [**UISim**](https://arxiv.org/abs/2509.21733) (arXiv, 2025) — Interactive image-based UI simulator for dynamic mobile environments.
+ [**ViMo**](https://arxiv.org/abs/2504.13936) (arXiv, 2025) — Generative visual GUI world model for app agents.
+ [**MobileWorldBench**](https://arxiv.org/abs/2512.14014) (arXiv, 2025) — Towards semantic world modeling for mobile agents.

### Cross-Domain GUI/Web

+ [**SimuRA**](https://arxiv.org/abs/2507.23773) (arXiv, 2025) — World-model-driven simulative reasoning architecture for goal-oriented agents.
+ [**VAGEN**](https://arxiv.org/abs/2510.16907) (arXiv, 2025) — Reinforcing world model reasoning for multi-turn VLM agents.
+ [**EvoAgent**](https://arxiv.org/abs/2502.05907) (arXiv, 2025) — Self-evolving agent with continual world model for long-horizon tasks.
+ [**WorldGPT**](https://doi.org/10.1145/3664647.3681649) (ACM MM, 2024) — Empowering LLMs as multimodal world models.

## Tool Use

World models for tool-augmented agents, API interaction, and workflow systems.

+ [**Agent World Model**](https://arxiv.org/abs/2602.10090) (arXiv, 2026) — Infinity synthetic environments for agentic RL. [![Stars](https://img.shields.io/github/stars/Snowflake-Labs/agent-world-model?style=flat&logo=github&color=181717)](https://github.com/Snowflake-Labs/agent-world-model)
+ [**RWML**](https://arxiv.org/abs/2602.05842) (arXiv, 2026) — Reinforcement world model learning for LLM-based agents.
+ [**World of Workflows**](https://arxiv.org/abs/2601.22130) (arXiv, 2026) — Benchmark for bringing world models to enterprise systems. [![Stars](https://img.shields.io/github/stars/Skyfall-Research/world-of-workflows?style=flat&logo=github&color=181717)](https://github.com/Skyfall-Research/world-of-workflows)
+ [**GTM**](https://arxiv.org/abs/2512.04535) (arXiv, 2025) — Simulating the world of tools for AI agents.
+ [**LLMs as Simulators**](https://arxiv.org/abs/2510.14969) (arXiv, 2025) — LLMs as scalable, general-purpose simulators for digital agent training.
+ [**ToolRM**](https://arxiv.org/abs/2509.11963) (arXiv, 2025) — Outcome reward models for tool-calling LLMs.

## Code

World models for code generation, software engineering, and executable environment modeling.

+ [**SWE-World**](https://arxiv.org/abs/2602.03419) (arXiv, 2026) — Building software engineering agents in docker-free surrogate environments. [![Stars](https://img.shields.io/github/stars/RUCAIBox/SWE-World?style=flat&logo=github&color=181717)](https://github.com/RUCAIBox/SWE-World)
+ [**CWM**](https://arxiv.org/abs/2510.02387) (arXiv, 2025) — Open-weights LLM for code generation with world models.
+ [**Code World Models (GIF-MCTS)**](https://arxiv.org/abs/2405.15383) (arXiv, 2024) — Generating code world models with LLMs guided by MCTS. [![Stars](https://img.shields.io/github/stars/nicoladainese96/code-world-models?style=flat&logo=github&color=181717)](https://github.com/nicoladainese96/code-world-models)
+ [**WorldCoder**](https://arxiv.org/abs/2402.12275) (NeurIPS, 2024) — Model-based LLM agent that builds world models by writing code.

## Benchmarks & Environments

### Games

+ [**Atari 200M**](https://doi.org/10.1038/nature14236) (Nature, 2015) — Visual dynamics modeling under long-horizon control. [![Stars](https://img.shields.io/github/stars/Farama-Foundation/Arcade-Learning-Environment?style=flat&logo=github&color=181717)](https://github.com/Farama-Foundation/Arcade-Learning-Environment)
+ [**Atari 100k**](https://arxiv.org/abs/2111.00210) (NeurIPS, 2021) — Sample-efficient rollout learning from limited data. [![Stars](https://img.shields.io/github/stars/YeWR/EfficientZero?style=flat&logo=github&color=181717)](https://github.com/YeWR/EfficientZero)
+ [**BabyAI**](https://arxiv.org/abs/1810.08272) (ICLR, 2019) — Grounded language-conditioned planning. [![Stars](https://img.shields.io/github/stars/mila-iqia/babyai?style=flat&logo=github&color=181717)](https://github.com/mila-iqia/babyai)
+ [**SMAC**](https://arxiv.org/abs/1902.04043) (AAMAS, 2019) — Multi-agent state evolution and coordination-sensitive rollout. [![Stars](https://img.shields.io/github/stars/oxwhirl/smac?style=flat&logo=github&color=181717)](https://github.com/oxwhirl/smac)
+ [**SMACv2**](https://arxiv.org/abs/2212.07489) (arXiv, 2022) — Harder stochastic branching and robust multi-agent rollout. [![Stars](https://img.shields.io/github/stars/oxwhirl/smacv2?style=flat&logo=github&color=181717)](https://github.com/oxwhirl/smacv2)
+ [**Procgen**](https://arxiv.org/abs/1912.01588) (ICML, 2020) — Generalization under procedurally varying dynamics. [![Stars](https://img.shields.io/github/stars/openai/procgen?style=flat&logo=github&color=181717)](https://github.com/openai/procgen)
+ [**NetHack**](https://arxiv.org/abs/2006.13760) (NeurIPS, 2020) — Partial observability and long-horizon symbolic-visual state tracking. [![Stars](https://img.shields.io/github/stars/NetHack-LE/nle?style=flat&logo=github&color=181717)](https://github.com/NetHack-LE/nle)
+ [**MiniHack**](https://arxiv.org/abs/2109.13202) (arXiv, 2021) — Modular long-horizon transition modeling across diverse tasks. [![Stars](https://img.shields.io/github/stars/NetHack-LE/minihack?style=flat&logo=github&color=181717)](https://github.com/NetHack-LE/minihack)
+ [**Crafter**](https://arxiv.org/abs/2109.06780) (arXiv, 2021) — Persistent survival-state dynamics and open-ended progression. [![Stars](https://img.shields.io/github/stars/danijar/crafter?style=flat&logo=github&color=181717)](https://github.com/danijar/crafter)
+ [**Minigrid**](https://arxiv.org/abs/2306.13831) (arXiv, 2023) — Compact planning under partially observable gridworld dynamics. [![Stars](https://img.shields.io/github/stars/Farama-Foundation/Minigrid?style=flat&logo=github&color=181717)](https://github.com/Farama-Foundation/Minigrid)
+ [**TextWorld**](https://arxiv.org/abs/1806.11532) (CGW@IJCAI, 2018) — Long-horizon symbolic transitions and command-conditioned dynamics. [![Stars](https://img.shields.io/github/stars/Microsoft/TextWorld?style=flat&logo=github&color=181717)](https://github.com/Microsoft/TextWorld)
+ [**ALFWorld**](https://arxiv.org/abs/2010.03768) (ICLR, 2021) — Multi-step symbolic planning with delayed consequences. [![Stars](https://img.shields.io/github/stars/alfworld/alfworld?style=flat&logo=github&color=181717)](https://github.com/alfworld/alfworld)
+ [**ScienceWorld**](https://arxiv.org/abs/2203.07540) (EMNLP, 2022) — Causal reasoning over structured textual world state. [![Stars](https://img.shields.io/github/stars/allenai/ScienceWorld?style=flat&logo=github&color=181717)](https://github.com/allenai/ScienceWorld)
+ [**PlanCraft**](https://arxiv.org/abs/2412.21033) (arXiv, 2024) — Structured planning over branching crafting dependencies. [![Stars](https://img.shields.io/github/stars/gautierdag/plancraft?style=flat&logo=github&color=181717)](https://github.com/gautierdag/plancraft)

### Web & GUI

+ [**World of Bits**](https://arxiv.org/abs/1704.07433) (ICML, 2017) — Open-domain web-state transitions under interface interaction. [![Stars](https://img.shields.io/github/stars/stanfordnlp/wob?style=flat&logo=github&color=181717)](https://github.com/stanfordnlp/wob)
+ [**MiniWoB++**](https://arxiv.org/abs/1802.08802) (arXiv, 2018) — Short-horizon UI changes with typed web actions. [![Stars](https://img.shields.io/github/stars/Farama-Foundation/miniwob-plusplus?style=flat&logo=github&color=181717)](https://github.com/Farama-Foundation/miniwob-plusplus)
+ [**WebShop**](https://arxiv.org/abs/2207.01206) (NeurIPS, 2022) — Workflow branching and latent task progress in shopping interfaces. [![Stars](https://img.shields.io/github/stars/princeton-nlp/WebShop?style=flat&logo=github&color=181717)](https://github.com/princeton-nlp/WebShop)
+ [**WebArena**](https://arxiv.org/abs/2307.13854) (ICLR, 2024) — Semantic UI transitions under realistic web workflows. [![Stars](https://img.shields.io/github/stars/web-arena-x/webarena?style=flat&logo=github&color=181717)](https://github.com/web-arena-x/webarena)
+ [**VisualWebArena**](https://arxiv.org/abs/2401.13649) (arXiv, 2024) — Multimodal web-state prediction with visual-semantic grounding. [![Stars](https://img.shields.io/github/stars/web-arena-x/visualwebarena?style=flat&logo=github&color=181717)](https://github.com/web-arena-x/visualwebarena)
+ [**TheAgentCompany**](https://arxiv.org/abs/2412.14161) (arXiv, 2024) — Enterprise-style browser workflows and hidden application logic. [![Stars](https://img.shields.io/github/stars/TheAgentCompany/TheAgentCompany?style=flat&logo=github&color=181717)](https://github.com/TheAgentCompany/TheAgentCompany)
+ [**OSWorld**](https://arxiv.org/abs/2404.07972) (arXiv, 2024) — Open-ended computer-use transitions across apps and OS state. [![Stars](https://img.shields.io/github/stars/xlang-ai/OSWorld?style=flat&logo=github&color=181717)](https://github.com/xlang-ai/OSWorld)
+ [**WindowsAgentArena**](https://arxiv.org/abs/2409.08264) (arXiv, 2024) — Real multi-app state coordination under desktop interaction. [![Stars](https://img.shields.io/github/stars/microsoft/WindowsAgentArena?style=flat&logo=github&color=181717)](https://github.com/microsoft/WindowsAgentArena)
+ [**OmniACT**](https://arxiv.org/abs/2402.17553) (arXiv, 2024) — Executable computer-use actions with cross-platform UI effects.
+ [**AndroidWorld**](https://arxiv.org/abs/2405.14573) (arXiv, 2024) — Dynamic mobile UI transitions under touch interaction. [![Stars](https://img.shields.io/github/stars/google-research/android_world?style=flat&logo=github&color=181717)](https://github.com/google-research/android_world)
+ [**MobileWorld**](https://arxiv.org/abs/2512.19432) (arXiv, 2025) — Mobile workflows with user interaction and MCP-augmented tasks. [![Stars](https://img.shields.io/github/stars/Tongyi-MAI/MobileWorld?style=flat&logo=github&color=181717)](https://github.com/Tongyi-MAI/MobileWorld)
+ [**GUI-360°**](https://arxiv.org/abs/2511.04307) (arXiv, 2025) — Comprehensive dataset and benchmark for computer-using agents.

### Tool Use

+ [**τ-bench**](https://arxiv.org/abs/2406.12045) (arXiv, 2024) — Typed tool-state updates in tool-agent-user interaction. [![Stars](https://img.shields.io/github/stars/sierra-research/tau-bench?style=flat&logo=github&color=181717)](https://github.com/sierra-research/tau-bench)
+ [**τ²-bench**](https://arxiv.org/abs/2506.07982) (arXiv, 2025) — Multi-party control and persistent tool-state consistency. [![Stars](https://img.shields.io/github/stars/sierra-research/tau2-bench?style=flat&logo=github&color=181717)](https://github.com/sierra-research/tau2-bench)
+ [**τ³-bench**](https://arxiv.org/abs/2603.13686) (arXiv, 2026) — Voice-grounded tool use with multimodal state tracking.
+ [**BFCL v3**](https://gorilla.cs.berkeley.edu/blogs/13_bfcl_v3_multi_turn.html) (ICML, 2025) — Multi-turn function-call validity and argument correctness.
+ [**MCP-Universe**](https://arxiv.org/abs/2508.14704) (arXiv, 2025) — Multi-server tool coordination and external-state mutation. [![Stars](https://img.shields.io/github/stars/SalesforceAIResearch/MCP-Universe?style=flat&logo=github&color=181717)](https://github.com/SalesforceAIResearch/MCP-Universe)
+ [**World of Workflows**](https://arxiv.org/abs/2601.22130) (arXiv, 2026) — Enterprise workflow transitions with hidden service-side dependencies. [![Stars](https://img.shields.io/github/stars/Skyfall-Research/world-of-workflows?style=flat&logo=github&color=181717)](https://github.com/Skyfall-Research/world-of-workflows)
+ [**AgentWorldModel-1K**](https://arxiv.org/abs/2602.10090) (arXiv, 2026) — Synthetic external-state modeling in executable SQL-MCP ecosystems. [![Stars](https://img.shields.io/github/stars/Snowflake-Labs/agent-world-model?style=flat&logo=github&color=181717)](https://github.com/Snowflake-Labs/agent-world-model)

### Code

+ [**HumanEval**](https://arxiv.org/abs/2107.03374) (arXiv, 2021) — Executable outcome prediction for code generation. [![Stars](https://img.shields.io/github/stars/openai/human-eval?style=flat&logo=github&color=181717)](https://github.com/openai/human-eval)
+ [**SWE-bench**](https://arxiv.org/abs/2310.06770) (ICLR, 2024) — Repository-scale state evolution under code edits and tests. [![Stars](https://img.shields.io/github/stars/swe-bench/SWE-bench?style=flat&logo=github&color=181717)](https://github.com/swe-bench/SWE-bench)
+ [**InterCode**](https://arxiv.org/abs/2306.14898) (arXiv, 2023) — Interactive coding dynamics with stepwise execution feedback. [![Stars](https://img.shields.io/github/stars/princeton-nlp/intercode?style=flat&logo=github&color=181717)](https://github.com/princeton-nlp/intercode)
+ [**SWE-World**](https://arxiv.org/abs/2602.03419) (arXiv, 2026) — Software-engineering transitions with surrogate environment feedback. [![Stars](https://img.shields.io/github/stars/RUCAIBox/SWE-World?style=flat&logo=github&color=181717)](https://github.com/RUCAIBox/SWE-World)

### Multi-Domain

+ [**AgentGym**](https://arxiv.org/abs/2406.04151) (arXiv, 2024) — Transfer of predictive abstractions across heterogeneous environments. [![Stars](https://img.shields.io/github/stars/WooooDyy/AgentGym?style=flat&logo=github&color=181717)](https://github.com/WooooDyy/AgentGym)
+ [**AgentBench**](https://arxiv.org/abs/2308.03688) (arXiv, 2023) — Cross-domain comparison of agent behavior and predictive utility. [![Stars](https://img.shields.io/github/stars/THUDM/AgentBench?style=flat&logo=github&color=181717)](https://github.com/THUDM/AgentBench)

## Datasets

| Supervision Type | Representative Datasets | Role in World Models |
|:-----------------|:-----------------------|:---------------------|
| **Action-conditioned transitions** | [Mind2Web](https://arxiv.org/abs/2306.06070), [Android in the Wild](https://arxiv.org/abs/2307.10088), [Android Control](https://arxiv.org/abs/2406.12045), [MobileWorldBench](https://arxiv.org/abs/2512.14014) | Semantic UI dynamics, DOM/screenshot deltas, next-state prediction |
| **Trajectory demonstrations** | [GUI-360°](https://arxiv.org/abs/2511.04307), [WebLINX](https://arxiv.org/abs/2312.07930), [AMEX](https://arxiv.org/abs/2407.17490), [Atari-HEAD](https://arxiv.org/abs/1903.06754), [VPT](https://arxiv.org/abs/2206.11795) | Planning priors, long-range workflow structure, temporal abstraction |
| **Execution-grounded supervision** | [APPS](https://arxiv.org/abs/2105.09938), [MBPP](https://arxiv.org/abs/2108.07732), [CodeXGLUE](https://arxiv.org/abs/2102.04664), [HumanEval](https://arxiv.org/abs/2107.03374) | Constraint-aware prediction, execution-grounded transition modeling |
| **Tool interaction traces** | [ToolBench](https://arxiv.org/abs/2307.16789), [ToolAlpaca](https://arxiv.org/abs/2306.05301), [API-Bank](https://arxiv.org/abs/2304.08244) | Schema-constrained actions, external system dynamics, tool workflows |
| **Foundation corpora** | [The Stack](https://arxiv.org/abs/2211.15533), [StarCoder Data](https://arxiv.org/abs/2305.06161) | Reusable semantic priors, representation quality, cross-domain generalization |
| **Synthetic trajectories** | [WebWorld](https://arxiv.org/abs/2602.14721), [Agent World Model](https://arxiv.org/abs/2602.10090) | Counterfactual transitions, branch expansion, planning robustness |

## Related Surveys

+ [**Dong et al.**](https://arxiv.org/abs/2501.00000) (Authorea, 2026) — Learning to model the world: world models in AI.
+ [**Tan et al.**](https://arxiv.org/abs/2501.00000) (Authorea, 2026) — Towards generalist embodied AI: world models for VLA agents.
+ [**Bai et al.**](https://arxiv.org/abs/2510.20668) (arXiv, 2025) — From masks to worlds: a hitchhiker's guide to world models.
+ [**Kong et al.**](https://arxiv.org/abs/2509.07996) (arXiv, 2025) — 3D and 4D world modeling.
+ [**Li et al.**](https://arxiv.org/abs/2510.16732) (arXiv, 2025) — Comprehensive survey on world models for embodied AI.
+ [**Long et al.**](https://arxiv.org/abs/2507.00917) (arXiv, 2025) — Learning embodied intelligence from physical simulators and world models.
+ [**Zhang et al.**](https://arxiv.org/abs/2511.02097) (arXiv, 2025) — Robotic manipulation world models.
+ [**Tu et al.**](https://arxiv.org/abs/2502.10498) (arXiv, 2025) — Autonomous driving world models.
+ [**Feng et al.**](https://arxiv.org/abs/2501.11260) (arXiv, 2025) — Survey of world models for autonomous driving.
+ [**Ding et al.**](https://arxiv.org/abs/2411.14499) (ACM CSUR, 2025) — Understanding world or predicting future? comprehensive survey.
+ [**Zhu et al.**](https://arxiv.org/abs/2405.03520) (arXiv, 2024) — Is Sora a world simulator? general world models and beyond.
+ [**Wang et al.**](https://arxiv.org/abs/2308.11432) (Frontiers, 2023) — Survey on LLM-based autonomous agents.

## Welcome to Contribute

**We welcome contributions!** This project is actively maintained. If you know a paper or benchmark that should be listed, please open an issue or submit a pull request.

When submitting, please include:
- **Title** and **paper URL** (arXiv or publication link)
- **Venue** and **year**
- **Target section** (Games / Web & GUI / Tool Use / Code / Benchmarks)
- **One-line summary** of the contribution
- **Code URL** (optional, for GitHub stars badge)

## Citation

If you find this resource useful, please cite our survey:

```bibtex
@article{survey2026digitalagentsworldmodels,
  title         = {Digital Agents Meet World Models: A Survey},
  author        = {AI Agent Team},
  year          = {2026},
  eprint        = {XXXX.XXXXX},
  archivePrefix = {arXiv},
  primaryClass  = {cs.AI},
  url           = {https://arxiv.org/abs/XXXX.XXXXX}
}
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=YOUR-ORG/awesome-world-models-for-digital-agents&type=Date)](https://www.star-history.com/#YOUR-ORG/awesome-world-models-for-digital-agents&Date)
