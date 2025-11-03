# 🎰 Exploring the Multi-Armed Bandit Problem

This project investigates several elegant strategies for addressing the classic **multi-armed bandit challenge**—a scenario where a gambler faces a row of slot machines (one-armed bandits), each with different, unknown payout probabilities. This represents a foundational problem in **online reinforcement learning**, where an agent must learn optimal behavior through trial and error.

The problem has profound practical applications across diverse domains: `digital marketing campaigns`, `recommendation systems`, `adaptive clinical trials`, and `algorithmic trading`. At its heart lies a fundamental tension: the **exploration-exploitation tradeoff**—balancing the discovery of potentially better options against leveraging what's already known to work well.

## 📋 What This Notebook Contains

### 🎯 Bandit Environment
A simulation class that models the **N-armed Bernoulli bandit**, where each arm operates as an independent, stationary `Bernoulli process` with fixed but unknown reward probabilities.

### ⚙️ Simulation Harness
An experimental framework that orchestrates interactions between `decision policies` and the `bandit environment`, tracking performance metrics over time.

### 🧠 Policy Implementations
Four distinct algorithms, each coded from scratch and rigorously compared:

**1. Random Selection**  
A baseline strategy providing uniform exploration—arms are selected with **equal probability**, establishing a performance lower bound.

**2. ε-Greedy**  
A simple yet effective approach that exploits the current best arm with probability `(1-ε)`, while exploring randomly with probability `ε`.

**3. Bayesian UCB**  
A sophisticated method leveraging **Bayesian posterior credible intervals** (`95%`) to balance optimism about uncertain arms with confidence in well-explored ones.

**4. Thompson Sampling**  
An elegant **probability matching strategy** that samples from `Beta posterior distributions`, naturally balancing exploration and exploitation through randomization.

## 📦 Dependencies

```python
import random
import numpy as np
import matplotlib.pyplot as plt
from scipy import stats
```

**Required Libraries:**
- `random` (standard library)
- `numpy` for numerical computations
- `matplotlib` for visualization
- `scipy` for statistical functions

## 🚀 Getting Started

Run the notebook to compare the performance of different bandit algorithms across various scenarios. The simulation framework allows for customization of parameters including:

- `number of arms`
- `reward probabilities`
- `time horizon`
- `exploration parameters`

## 🎓 Learning Objectives

- Understand the **exploration-exploitation tradeoff**
- Implement classic **bandit algorithms** from scratch
- Compare algorithm performance through **simulation**
- Gain insights into **online learning** and decision making under uncertainty

## 💡 Key Insights

This notebook provides both **theoretical insights** and **practical implementations**, making it an ideal resource for understanding how intelligent agents learn to make optimal decisions under uncertainty.

## 📊 Use Cases

**Digital Marketing**: `A/B testing` and campaign optimization  
**Recommendation Systems**: Content personalization and `user engagement`  
**Clinical Trials**: `Adaptive treatment allocation`  
**Financial Trading**: Portfolio optimization and `strategy selection`
