# 🎰 Exploring the Multi-Armed Bandit Problem

This project impliments algorithms for addressing the classic **multi-armed bandit problem**, a scenario where a gambler faces a row of slot machines (one-armed bandits), each with different, unknown payout probabilities. This represents a foundational problem in **online reinforcement learning**, where an agent must learn optimal behavior through trial and error.

The problem has  practical applications across diverse domains: `digital marketing campaigns`, `recommendation systems`, `adaptive clinical trials`, and `algorithmic trading`. At its heart lies a fundamental tradeoff of the **exploration-exploitation** i.e balancing the discovery of potentially better options against leveraging what's already known to work well.

## 📋 What This Notebook Contains

### 🎯 Bandit Environment
We've built a simulation class for the `N-armed Bernoulli bandit`. Think of it as a virtual casino where each slot machine (arm) has its own secret win rate that stays constant but you don't know what it is until you start playing.

### ⚙️ Simulation
An experimental roll play that records interactions between `decision policies` and the `bandit environment`, tracking performance metrics over time.

### 🧠 Policy Implementations
I have explained, implemented and compared four algorithms

**1. Random Selection**  

A baseline strategy providing uniform exploration—arms are selected with **equal probability** at each timestep. This approach assumes no prior knowledge and gathers unbiased reward samples from all arms, making it useful for establishing a **performance lower bound** or as a **control policy** in stochastic bandit experiments.

---

**2. ε-Greedy**  

A simple yet effective approach that exploits the **empirically best arm** (highest mean reward estimate) with probability (1−ε) and explores randomly with probability ε. The reward estimates are updated incrementally based on observed rewards, allowing continuous refinement of value estimates. This strategy balances exploration and exploitation via a tunable ε parameter, often decayed over time to favor exploitation after sufficient exploration.

---

**3. Bayesian UCB** 

It leverages **Bayesian posterior credible intervals**, typically the upper quantile of a Beta(α, β) distribution, to form an **upper confidence bound (UCB)** for each arm. At each step, the arm with the highest upper bound is selected, promoting arms that are both promising and uncertain. This integrates **uncertainty-aware optimism**, balancing exploration of high-variance arms with exploitation of well-sampled ones, and often yields lower regret than classical UCB in stochastic environments.

---

**4. Thompson Sampling**

A **probability matching strategy** that samples reward probabilities directly from **posterior Beta distributions** for each arm. At every round, it draws one sample per arm and selects the arm with the highest sampled value. This randomized selection naturally balances **exploration and exploitation**, adapting posterior uncertainty over time, and achieves **asymptotically optimal regret** for many bandit formulations.


## 📦 Dependencies (Required Libraries:)
- `random` (standard library)
- `numpy` for numerical computations
- `matplotlib` for visualization
- `scipy` for statistical functions

## 🚀 Getting Started

Run the notebook to compare the performance of different bandit algorithms across various scenarios. During simulation you can customize the following parameters:

- `number of arms`
- `reward probabilities`
- `time horizon`
- `exploration parameters`

## 🎓 Learning Objectives

- Understand the **exploration-exploitation tradeoff**
- Implement classic **bandit algorithms** from scratch
- Compare algorithm performance through **simulation**

## 📊 Use Cases

**Digital Marketing**: `A/B testing` and campaign optimization  
**Recommendation Systems**: Content personalization and `user engagement`  
**Clinical Trials**: `Adaptive treatment allocation`  
**Financial Trading**: Portfolio optimization and `strategy selection`
