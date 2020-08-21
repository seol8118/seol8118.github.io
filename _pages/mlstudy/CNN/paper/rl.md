---
title: "Reinforcement Learning"
permalink: /rlPaper/
sidebar:
  nav: sidebar-rl
author_profile: false
header:
  overlay_image: /assets/images/dataScience.jpg
  overlay_filter: 0.5
---
# 1. Model-Free RL
## a. Deep Q-Learning
[1]	Playing Atari with Deep Reinforcement Learning, Mnih et al, 2013. Algorithm: DQN.
[2]	Deep Recurrent Q-Learning for Partially Observable MDPs, Hausknecht and Stone, 2015. Algorithm: Deep Recurrent Q-Learning.
[3]	Dueling Network Architectures for Deep Reinforcement Learning, Wang et al, 2015. Algorithm: Dueling DQN.
[4]	Deep Reinforcement Learning with Double Q-learning, Hasselt et al 2015. Algorithm: Double DQN.
[5]	Prioritized Experience Replay, Schaul et al, 2015. Algorithm: Prioritized Experience Replay (PER).
[6]	Rainbow: Combining Improvements in Deep Reinforcement Learning, Hessel et al, 2017. Algorithm: Rainbow DQN.

## b. Policy Gradients
[7]	Asynchronous Methods for Deep Reinforcement Learning, Mnih et al, 2016. Algorithm: A3C.
[8]	Trust Region Policy Optimization, Schulman et al, 2015. Algorithm: TRPO.
[9]	High-Dimensional Continuous Control Using Generalized Advantage Estimation, Schulman et al, 2015. Algorithm: GAE.
[10]	Proximal Policy Optimization Algorithms, Schulman et al, 2017. Algorithm: PPO-Clip, PPO-Penalty.
[11]	Emergence of Locomotion Behaviours in Rich Environments, Heess et al, 2017. Algorithm: PPO-Penalty.
[12]	Scalable trust-region method for deep reinforcement learning using Kronecker-factored approximation, Wu et al, 2017. Algorithm: ACKTR.
[13]	Sample Efficient Actor-Critic with Experience Replay, Wang et al, 2016. Algorithm: ACER.
[14]	Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor, Haarnoja et al, 2018. Algorithm: SAC.

## c. Deterministic Policy Gradients
[15]	Deterministic Policy Gradient Algorithms, Silver et al, 2014. Algorithm: DPG.
[16]	Continuous Control With Deep Reinforcement Learning, Lillicrap et al, 2015. Algorithm: DDPG.
[17]	Addressing Function Approximation Error in Actor-Critic Methods, Fujimoto et al, 2018. Algorithm: TD3.

## d. Distributional RL
[18]	A Distributional Perspective on Reinforcement Learning, Bellemare et al, 2017. Algorithm: C51.
[19]	Distributional Reinforcement Learning with Quantile Regression, Dabney et al, 2017. Algorithm: QR-DQN.
[20]	Implicit Quantile Networks for Distributional Reinforcement Learning, Dabney et al, 2018. Algorithm: IQN.
[21]	Dopamine: A Research Framework for Deep Reinforcement Learning, Anonymous, 2018. Contribution: Introduces Dopamine, a code repository containing implementations of DQN, C51, IQN, and Rainbow. Code link.
e. Policy Gradients with Action-Dependent Baselines
[22]	Q-Prop: Sample-Efficient Policy Gradient with An Off-Policy Critic, Gu et al, 2016. Algorithm: Q-Prop.
[23]	Action-depedent Control Variates for Policy Optimization via Stein’s Identity, Liu et al, 2017. Algorithm: Stein Control Variates.
[24]	The Mirage of Action-Dependent Baselines in Reinforcement Learning, Tucker et al, 2018. Contribution: interestingly, critiques and reevaluates claims from earlier papers (including Q-Prop and stein control variates) and finds important methodological errors in them.
f. Path-Consistency Learning
[25]	Bridging the Gap Between Value and Policy Based Reinforcement Learning, Nachum et al, 2017. Algorithm: PCL.
[26]	Trust-PCL: An Off-Policy Trust Region Method for Continuous Control, Nachum et al, 2017. Algorithm: Trust-PCL.
g. Other Directions for Combining Policy-Learning and Q-Learning
[27]	Combining Policy Gradient and Q-learning, O’Donoghue et al, 2016. Algorithm: PGQL.
[28]	The Reactor: A Fast and Sample-Efficient Actor-Critic Agent for Reinforcement Learning, Gruslys et al, 2017. Algorithm: Reactor.
[29]	Interpolated Policy Gradient: Merging On-Policy and Off-Policy Gradient Estimation for Deep Reinforcement Learning, Gu et al, 2017. Algorithm: IPG.
[30]	Equivalence Between Policy Gradients and Soft Q-Learning, Schulman et al, 2017. Contribution: Reveals a theoretical link between these two families of RL algorithms.
h. Evolutionary Algorithms
[31]	Evolution Strategies as a Scalable Alternative to Reinforcement Learning, Salimans et al, 2017. Algorithm: ES.

# 3. Transfer and Multitask RL
[50]	Hindsight Experience Replay, Andrychowicz et al, 2017. Algorithm: Hindsight Experience Replay (HER).

# 6. Model-Based RL
[66]	Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm, Silver et al, 2017. Algorithm: AlphaZero.
