---
layout: post
title: "Week 2 — Smart Task Allocation with Multi-Armed Bandits"
date: 2025-06-13 10:00:00 +0800
categories: [blog]
tags: [gsoc, sustainhub, opensource, mab, agent-based-modeling, python]
author: Vidhi Rohira
---

Welcome back to my second blog post for GSoC 2025, where I continue to build SustainHub — an agent-based simulation framework for modeling open-source community dynamics.

## Week 2: Smarter Task Allocation with MAB

This week, I focused on improving the task assignment logic by implementing a Multi-Armed Bandit (MAB) strategy, specifically Thompson Sampling, to dynamically match agents with tasks.

### What I implemented:

I replaced the earlier rule-based strategy with a probabilistic approach based on Thompson Sampling. The aim was to build a system that can learn over time which agents are better suited for specific types of tasks, while still occasionally exploring less-utilized agents.

The allocator works by balancing two core ideas:
- Exploration: occasionally trying out agents who have taken on fewer tasks to gather more information about their performance.
- Exploitation: favoring agents with a strong track record of success in similar tasks.

Each agent maintains a record of successful and failed attempts per task type. These records are then used to sample from a beta distribution, which allows the system to estimate the likelihood of success for a given agent and task pairing.

### Why Thompson Sampling?

Thompson Sampling offers a Bayesian solution to the exploration-exploitation trade-off. It allows agents with limited data to still be considered, while naturally favoring agents that have performed well. This helps avoid bias toward only experienced agents and supports discovering new potential within the community.

### Key Learnings:

- Task allocation benefits greatly from adaptive strategies that incorporate learning and uncertainty.
- Probabilistic reasoning helps in making fair and informed decisions, even when data is sparse.
- Thompson Sampling provides a practical and interpretable solution for dynamic allocation problems in agent-based systems.

### Next Up (Week 3 Goals):

- Implement learning feedback where agents can improve their expertise after completing tasks.
- Model task dependencies and simulate collaborative task resolution.
- Begin initial development of visualization tools for analyzing system performance and agent behavior.

Thank you for reading, and I look forward to sharing more updates as SustainHub continues to evolve.

— Vidhi Rohira
