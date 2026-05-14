---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Research Interests
======
AI for Mental Health, Large Language Models for Psychological Counseling, Knowledge Editing, Theory-Grounded Dialogue Systems

Education
======
* M.S. in Computer Application Technology, Capital Normal University, Beijing, 2023 – Present
* B.S. in Internet of Things Engineering, Southwest Petroleum University, Chengdu, 2019 – 2023

Publications
======
1. Bowen Tian\*, **Caixue He**\*, Jiemin Wu, Jingying Wang, Wenshuo Chen, Zexi Li, Yutao Yue. "AnyEdit++: Adaptive Long-Form Knowledge Editing via Bayesian Surprise." *International Conference on Machine Learning (ICML)*, 2026. [\* Equal contribution]
2. **Caixue He**, Wei Song, Miaomiao Cheng, Xu Han. "LLM-MDP: Marrying Large Language Models with Markov Decision Processes for Structured CBT Session Guidance." *Manuscript in revision based on ACL 2026 reviewer feedback.*

Research Projects
======
**LLM-MDP: Structured Counseling Dialogue Generation via MDP** (2024 – 2025)
*First author. Capital Normal University.*
* Identified a core gap in mental health LLMs: CBT theory is typically used as static prompts or stylistic labels, not as structured constraints guiding dynamic therapy decisions.
* Formalized CBT single-session structure as a Markov Decision Process, with therapy stages as states, counseling techniques as actions, and stage-goal completion as rewards.
* Designed a full data pipeline: stage-labeled generation, rule-based filtering, structural validation via discourse perturbation, and iterative quality refinement.
* Constructed the MdpCBT dataset (~5,000 structured CBT dialogues); fine-tuned Qwen3-8B and achieved significant improvements over existing CBT-finetuned baselines on professionalism, empathy, and technique usage dimensions.

**AnyEdit++: Adaptive Long-Form Knowledge Editing** (2025 – 2026)
*Co-first author (2nd position). Collaborative Research.*
* Proposed Bayes-Chunk, an adaptive segmentation mechanism that dynamically identifies semantic boundaries based on Bayesian Surprise, replacing fixed-window chunking in prior knowledge editing pipelines.
* Established a theoretical framework with two principles: Structural Independence (cross-segment interference minimized via orthogonal anchor keys) and Causal Locality (semantic-peak updates yield superior control).
* Demonstrated superior performance on Llama 3.1 8B, Llama 2 7B, and Qwen 2.5 7B across mathematical reasoning, code generation, and narrative tasks.

Industry Experience
======
**Full-Stack Development Intern**, an AI-powered mental health counseling startup (May 2025 – Aug 2025)
* Designed and implemented the user memory module for cross-session counseling continuity — a key component for tracking long-term client states in mental health dialogue systems.
* Built real-time counseling dialogue infrastructure using Socket.IO with event dispatcher and intelligent multi-agent routing.
* Integrated LLM-enhanced features: multi-role AI counselor agents, RAG-based mental health knowledge QA, and long-term dialogue memory management.
* Developed WeChat mini-program frontend: counseling chat interface, MBTI assessment flow, and user profile management.
* Gained hands-on insight into the engineering and product challenges of deploying mental health LLMs in real-user scenarios.

Open Source Contributions
======
**Zino** (Rust, 1.1k+ stars) — Core Contributor, Open Source Promotion Plan, CAS (Jun 2025 – Sep 2025)
* 11 merged PRs, 100% merge rate.
* Implemented graph-based workflow engine for LLM automation pipelines (PR #154–#156).
* Designed Completion abstraction layer with streaming/non-streaming support for multiple LLM providers (PR #157, #159, #160).
* Built prompt templating, memory modules, embedding support, RAG vector retrieval, and tool calling (PR #161–#164).

Skills
======
* **Programming**: Python, Rust, C
* **ML / LLM Frameworks**: PyTorch, Hugging Face Transformers, PEFT (LoRA/QLoRA), LangChain
* **LLM Engineering**: Fine-tuning, RAG, Embedding, Streaming, Prompt Engineering, Agent Systems
* **Languages**: Chinese (native), English (working proficiency)
