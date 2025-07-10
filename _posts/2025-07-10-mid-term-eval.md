---
layout: post
title: "Midterm Evaluation — SustainHub's Evolution through GSoC 2025"
date: 2025-07-10 10:00:00 +0530
categories: [blog]
tags: [gsoc, sustainhub, midterm-evaluation, reinforcement-learning, agent-based-modeling, thompson-sampling, sarsa]
author: Vidhi Rohira
---

# Midterm Evaluation: Reflecting on the Journey of SustainHub

Hello everyone!  
As I reach the halfway point of my Google Summer of Code 2025 journey with the **Orthogonal Research and Education Lab**, I’m excited to share a detailed look back at the progress we’ve made so far on **SustainHub** — a simulation framework designed to model and improve open-source community dynamics through intelligent, learning-based agents.

---

## What is SustainHub?

**SustainHub** is not just a simulator — it’s a step toward rethinking open-source sustainability. We model contributors as autonomous agents who interact with tasks (like bug fixes, documentation, or features), adapt over time, and learn optimal strategies through **Reinforcement Learning (RL)**.

The vision:  
> To build a framework where agent behavior mirrors the complexity, collaboration, and learning found in real-world open-source communities.

This project blends ideas from:
- Multi-Armed Bandits (MAB)
- SARSA Reinforcement Learning
- Agent-Based Modeling
- Reward shaping and long-term adaptation
- Behavioral visualization and performance tracking

---

## Weekly Timeline Recap: Weeks 1 to 6

### Week 1: Foundations & Environment Setup
- Created a GitHub-inspired ecosystem with dynamic task queues and deadlines.
- Defined key agent roles:
  - Contributors (bug fixers)
  - Innovators (feature developers)
  - Knowledge Curators (documentation maintainers)
- Each agent initialized with realistic properties like task load, skill level, and success rate.
- Implemented rule-based task assignment as a baseline model.

Key Insight: Even a simple simulation requires deep thought on how human roles, deadlines, and complexity map to code.

---

### Week 2: Introducing Multi-Armed Bandits
- Replaced static rules with **Thompson Sampling**, a powerful Bayesian strategy for decision-making under uncertainty.
- Each agent keeps success/failure counts per task type, forming the basis for probabilistic task selection.
- Balanced exploration (trying less-tested agents) and exploitation (choosing high performers).

Why MAB?  
Traditional rule-based models can’t adapt. MAB gives agents the ability to learn what works and adjust task assignment probabilities dynamically.

Realization: Exploration isn't a bug — it's a feature that helps uncover hidden talent in a simulated open-source setting.

---

### Week 3: Optimizing MAB & Role Specialization
- Replaced ε-greedy logic with full Thompson Sampling that adapts in real time.
- Agents now specialize based on historic success:
  - Innovators were found completing ~70% of feature tasks.
  - Curators emerged with high documentation success.
- Visual analytics started to show emerging trends and team dynamics.

Major Milestone: MAB began identifying natural divisions in work — without any hard-coded labels. This emergent behavior mirrors how contributors in open-source communities grow into specific roles.

---

### Week 4: SARSA Agents & Realistic Learning
- Introduced **SARSA (State-Action-Reward-State-Action)** as a learning algorithm for agents.
- Each agent builds its own Q-Table, tracking expected rewards for `(state, action)` pairs.
- Role-specific rewards were added for completing preferred tasks:
  - Contributors: +3 for bug fixes
  - Innovators: +3 for feature tasks
  - Curators: +3 for documentation

Why SARSA?  
SARSA helps model on-policy learning, making agents learn while they work. This made their actions grounded in experience, not pre-programmed rules.

Breakthrough: For the first time, agents began showing personalized strategy evolution — some avoiding certain tasks, others taking calculated risks.

---

### Week 5: Scaling, Persistence & Analytics
- Increased the system scale from 10 to 15 agents, increasing interactions and diversity.
- Each agent now stores their Q-table persistently using JSON, allowing long-term learning across multiple runs.
- Developed a custom ε-greedy exploration strategy with:
  - Decay schedules over episodes
  - Role-based tuning
  - Contextual exploration bonuses

Behavior Visualization:
- Built real-time dashboards tracking:
  - Success rates
  - Role efficiency
  - Reward convergence
  - Q-value heatmaps

Impact: Visualizations reduced debugging time by ~40% and provided immediate clarity on agent behaviors.

Aha Moment: Seeing a clear dip in Q-values for overworked agents confirmed the need for load-balancing policies.

---

### Week 6: Realism, Policy Tuning, and Team Dynamics
- Fine-tuned SARSA hyperparameters (α=0.1, γ=0.9) for stability in noisy environments.
- Added intelligent load management:
  - Max task capacity enforced
  - Skipping tasks penalized with 0 reward
- System can now distinguish:
  - Burnout patterns
  - Underutilized talent
  - Over-specialization risks

Takeaway: The behavior of agents began to mirror real-world open-source contributors — sometimes overloaded, sometimes underappreciated, sometimes emerging as stars.

---

## Achievements So Far

### Feature Milestones
- Modular simulation environment
- MAB-based adaptive allocation
- SARSA learning agents
- Persistent agent memory (Q-tables)
- Role-based reward shaping
- Behavioral analytics and visualization

### Impact Metrics
- 68% exploitation of optimal strategies with healthy 32% exploration
- 83% task completion rate with intelligent role-task matching
- 40% debugging time reduction due to dashboards

### Open-Source Values Captured
- Emergence of roles
- Learning from mistakes
- Balancing fairness and performance
- Long-term contribution tracking

---

## Challenges Faced

| Challenge | How I Tackled It |
|----------|------------------|
| Reward shaping too generic | Added role-specific rewards with success/failure penalties |
| Agents overfitting roles | Introduced exploration decay and bonus incentives |
| Debugging Q-tables | Built heatmap visualizations for inspection |
| Task assignment loops | Designed load caps and skip logic |
| Persistent learning bugs | Implemented version-controlled JSON logging for Q-values |

---

## What's Next: Roadmap for Final Phase

### Collaborative Dynamics
- Simulate pair programming
- Introduce mentorship-like influence
- Model agent communication networks

### Hierarchical Reinforcement Learning
- Implement meta-agents who guide others
- Test high-level strategies for team coordination

### Reward Shaping & Motivation
- Add internal motivations (e.g., consistency, novelty)
- Dynamic reputation systems

### Transfer Learning
- Allow new agents to inherit behavior from successful ones
- Build generalizable learning frameworks

### Human-in-the-Loop Systems
- Design simple web interface for project maintainers to:
  - View dashboards
  - Intervene in task allocation
  - Train or test specific agents

---

## A Note of Gratitude

I am deeply grateful to my mentors at **OREL Lab** for their unwavering support, detailed code reviews, and thought-provoking discussions. Each idea, suggestion, and critique has helped evolve SustainHub into not just a simulator, but a living, learning system.

Special thanks to the broader GSoC community for being an inspiring and welcoming space. Every week, I learn not just from my project, but from reading others’ journeys.

---

## Final Thoughts

Working on SustainHub has been more than a technical project — it’s a lesson in community building, learning by doing, and respecting the nuances of real-world human systems. Open-source sustainability is not just about code; it’s about contributors, learning, feedback, and adaptation — and I’m thrilled that this simulation is beginning to reflect that reality.

As we head into the final phase, I’m excited to move from learning agents to collaborating agents, and from individual behavior to team-level intelligence.

Stay tuned.  
— Vidhi Rohira
