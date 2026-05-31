<div align="center">

# 🎾 Multi-Agent Tennis with MADDPG

### Deep Reinforcement Learning for Collaboration and Competition

![Python](https://img.shields.io/badge/Python-3.6+-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-EE4C2C?style=for-the-badge\&logo=pytorch\&logoColor=white)
![Reinforcement Learning](https://img.shields.io/badge/Reinforcement-Learning-success?style=for-the-badge)
![MADDPG](https://img.shields.io/badge/Algorithm-MADDPG-blue?style=for-the-badge)
![Multi Agent](https://img.shields.io/badge/Multi--Agent-Learning-purple?style=for-the-badge)
![Unity ML Agents](https://img.shields.io/badge/Unity-ML_Agents-black?style=for-the-badge\&logo=unity)
![Udacity](https://img.shields.io/badge/Udacity-DRL_Nanodegree-02B3E4?style=for-the-badge)

</div>

---

## Overview

This repository contains an implementation of a **Multi-Agent Deep Deterministic Policy Gradient (MADDPG)** system trained to solve the Unity ML-Agents Tennis environment.

Unlike traditional reinforcement learning tasks involving a single agent, this project explores how multiple autonomous agents can learn behaviours in a shared environment where collaboration and competition coexist.

The agents learn to coordinate their actions in order to keep a tennis ball in play for as long as possible while maximizing cumulative reward.

The project demonstrates key concepts in modern multi-agent reinforcement learning and distributed decision-making systems.

📄 **Project Report:** Detailed implementation notes, architecture decisions, hyperparameters, results, and future improvements are available in the accompanying report.

---

## Skills Demonstrated

* Multi-Agent Reinforcement Learning
* MADDPG (Multi-Agent Deep Deterministic Policy Gradients)
* Actor-Critic Architectures
* Continuous Control
* Autonomous Agents
* Distributed Learning Systems
* Neural Network Training
* PyTorch
* Unity ML-Agents
* Emergent Coordination

---

## Project Objective

![tennis](https://user-images.githubusercontent.com/39020690/64225910-6b833080-ceab-11e9-940e-be2597bf6b21.gif)

The goal is to train two autonomous agents capable of sustaining cooperative tennis rallies.

Each agent controls a racket and must learn how to position itself and interact with the ball effectively.

Rewards are assigned as follows:

| Event                          | Reward |
| ------------------------------ | ------ |
| Successful return over the net | +0.1   |
| Ball hits the ground           | -0.01  |
| Ball leaves the court          | -0.01  |

The challenge is not merely to maximize individual performance but to learn behaviours that allow both agents to maintain long rallies and achieve high cumulative scores.

---

## Environment Characteristics

| Property          | Value                  |
| ----------------- | ---------------------- |
| Observation Space | 8 continuous variables |
| Action Space      | 2 continuous actions   |
| Number of Agents  | 2                      |
| Environment       | Unity ML-Agents Tennis |
| Success Criterion | Average score ≥ 0.5    |

Each agent receives local observations including:

* Ball position
* Ball velocity
* Racket position
* Racket velocity

Available actions include:

* Movement toward or away from the net
* Jumping

---

## Multi-Agent Learning

This project extends beyond single-agent reinforcement learning by introducing multiple learning agents operating simultaneously within the same environment.

The agents must learn behaviours that support long-term success despite acting independently.

This introduces additional challenges such as:

* Non-stationary environments
* Coordination dynamics
* Shared reward structures
* Emergent cooperative behaviour

These concepts form the foundation of many modern multi-agent systems and autonomous decision architectures.

---

## Results

The trained agents successfully learned policies capable of solving the Tennis environment according to the project success criteria.

Trained model weights are included:

```text
agent1_checkpoint_actor.pth
agent1_checkpoint_critic.pth
agent2_checkpoint_actor.pth
agent2_checkpoint_critic.pth
```

The accompanying report discusses:

* MADDPG architecture
* Actor and critic networks
* Hyperparameter choices
* Training performance
* Lessons learned
* Potential future extensions

---

## Historical Context

This project was completed as part of the **Udacity Deep Reinforcement Learning Nanodegree**.

It represents the final project of the program and builds upon previous work involving:

* Deep Q-Networks (DQN)
* Continuous Control with DDPG
* Actor-Critic Architectures

The project marked an introduction to multi-agent learning systems and remains an important milestone in my exploration of autonomous agents, distributed AI systems, and reinforcement learning.


