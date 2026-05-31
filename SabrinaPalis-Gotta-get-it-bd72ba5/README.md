<div align="center">

# 🤖 Continuous Control with Deep Deterministic Policy Gradients (DDPG)

### Deep Reinforcement Learning for Robotic Arm Control

![Python](https://img.shields.io/badge/Python-3.6+-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-EE4C2C?style=for-the-badge\&logo=pytorch\&logoColor=white)
![Reinforcement Learning](https://img.shields.io/badge/Reinforcement-Learning-success?style=for-the-badge)
![DDPG](https://img.shields.io/badge/Algorithm-DDPG-blue?style=for-the-badge)
![Continuous Control](https://img.shields.io/badge/Task-Continuous_Control-purple?style=for-the-badge)
![Unity ML Agents](https://img.shields.io/badge/Unity-ML_Agents-black?style=for-the-badge\&logo=unity)
![Udacity](https://img.shields.io/badge/Udacity-DRL_Nanodegree-02B3E4?style=for-the-badge)

</div>

---

## Overview

This repository contains an implementation of a **Deep Deterministic Policy Gradient (DDPG)** agent trained to solve the Reacher continuous-control environment using **PyTorch** and **Unity ML-Agents**.

Unlike discrete-action reinforcement learning tasks, continuous control requires an agent to learn precise motor commands in a continuous action space. The challenge is similar to problems encountered in robotics, autonomous systems, and intelligent control.

The agent learns how to control a double-jointed robotic arm and maintain its position at a target location for as long as possible, maximizing cumulative reward through interaction with the environment.

📄 **Project Report:** Detailed discussion of the architecture, hyperparameters, training strategy, and results can be found in the accompanying report.

---

## Skills Demonstrated

* Deep Reinforcement Learning
* Deep Deterministic Policy Gradients (DDPG)
* Actor-Critic Architectures
* Continuous Control
* Robotic Manipulation
* Neural Network Training
* PyTorch
* Hyperparameter Tuning
* Unity ML-Agents
* Autonomous Decision Systems

---

## Project Objective

![20\_arms](https://user-images.githubusercontent.com/39020690/64061215-6bcab580-cba5-11e9-92ce-055a681ee005.gif)

The goal is to train a robotic arm capable of continuously tracking and reaching target positions within a simulated environment.

The agent receives a reward of **+0.1** for every timestep during which its hand remains inside the target region.

To maximize cumulative reward, the agent must learn smooth and stable control policies that maintain accurate positioning over extended periods.

---

## Environment Characteristics

| Property          | Value                   |
| ----------------- | ----------------------- |
| Observation Space | 33 continuous variables |
| Action Space      | 4 continuous actions    |
| Algorithm         | DDPG                    |
| Environment       | Unity ML-Agents Reacher |
| Success Criterion | Average score ≥ 30      |

The state vector contains:

* Position information
* Rotational information
* Velocities
* Angular velocities

Each action consists of four continuous values representing torques applied to the robotic arm joints.

---

## Distributed Reinforcement Learning

Two versions of the environment are available:

### Single-Agent Environment

One robotic arm learns independently.

### Multi-Agent Environment

Twenty identical agents interact with parallel copies of the environment simultaneously.

This configuration enables faster experience collection and supports reinforcement learning approaches that benefit from distributed training.

---

## Results

The trained agent successfully learned a continuous control policy capable of solving the Reacher environment according to the project performance criteria.

Trained model weights are included:

```text
checkpoint_actor.pth
checkpoint_critic.pth
```

The accompanying report provides additional information regarding:

* Network architecture
* Actor and critic design
* Hyperparameter selection
* Training performance
* Lessons learned and future improvements

---

## Historical Context

This project was completed as part of the **Udacity Deep Reinforcement Learning Nanodegree**.

It represents an important step from discrete-action reinforcement learning toward continuous control systems, actor-critic architectures, and robotics-inspired AI applications.

