<div align="center">

# 🍌 Banana Navigation with Deep Q-Networks

### Deep Reinforcement Learning using PyTorch and Unity ML-Agents

![Python](https://img.shields.io/badge/Python-3.6+-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-EE4C2C?style=for-the-badge\&logo=pytorch\&logoColor=white)
![Reinforcement Learning](https://img.shields.io/badge/Reinforcement-Learning-success?style=for-the-badge)
![DQN](https://img.shields.io/badge/Algorithm-DQN-blue?style=for-the-badge)
![Unity ML Agents](https://img.shields.io/badge/Unity-ML_Agents-black?style=for-the-badge\&logo=unity)
![Udacity](https://img.shields.io/badge/Udacity-DRL_Nanodegree-02B3E4?style=for-the-badge)

</div>

---

## Overview

This repository contains an implementation of a **Deep Q-Network (DQN)** agent trained to solve the Banana Navigation environment provided as part of the Udacity Deep Reinforcement Learning Nanodegree.

The project explores how an autonomous agent can learn effective navigation strategies through trial-and-error interaction with its environment. Using reinforcement learning, the agent gradually discovers how to maximize cumulative reward by collecting yellow bananas while avoiding blue bananas.

The implementation is written in **Python** and **PyTorch** and demonstrates several foundational reinforcement learning concepts, including:

* Deep Q-Networks (DQN)
* Experience Replay
* Target Networks
* Epsilon-Greedy Exploration
* Neural Network Function Approximation
* Sequential Decision Making

📄 **Project Report:** See the accompanying report for implementation details, hyperparameters, network architecture, results, and discussion.

---

## Skills Demonstrated

* Reinforcement Learning
* Deep Q-Learning
* PyTorch
* Neural Network Training
* Hyperparameter Tuning
* Agent Evaluation
* Unity ML-Agents
* Jupyter Notebooks

---

## Project Objective

<img src="https://user-images.githubusercontent.com/39020690/63669633-861d2180-c7a8-11e9-8973-458d65eb995f.gif">

The goal is to train an autonomous agent to navigate a virtual environment and maximize its cumulative reward.

The agent receives:

* **+1 reward** for collecting a yellow banana
* **−1 reward** for collecting a blue banana

The challenge is to learn an effective policy that consistently collects positive rewards while avoiding penalties.

### Environment Characteristics

| Property          | Value                                            |
| ----------------- | ------------------------------------------------ |
| State Space       | 37 dimensions                                    |
| Action Space      | 4 discrete actions                               |
| Environment       | Unity ML-Agents Banana Navigation                |
| Success Criterion | Average score ≥ 13 over 100 consecutive episodes |

Available actions:

| Action | Description   |
| ------ | ------------- |
| 0      | Move Forward  |
| 1      | Move Backward |
| 2      | Turn Left     |
| 3      | Turn Right    |

The state vector contains information about the agent's velocity and ray-based perception of nearby objects, allowing it to learn how to interact effectively with the environment.

---

## Results

The agent successfully learned a navigation policy capable of solving the environment according to the project requirements.

The trained model weights are provided in:

```text
project1_dqn_agent.pth
```

The full implementation, training procedure, architecture, hyperparameter choices, and future improvements are discussed in the accompanying project report.

---

## Historical Context

This project was completed as part of the **Udacity Deep Reinforcement Learning Nanodegree** and represents an early milestone in my study of autonomous decision systems and reinforcement learning.

It remains an important foundation for later work involving deep learning, AI systems, agent architectures, and autonomous decision-making frameworks.






