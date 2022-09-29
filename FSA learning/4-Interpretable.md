# Interpretable Sequence Classification via Discrete Optimization  

[TOC]



## Contributions

- In this work, we use discrete optimization to learn interpretable classifiers that favor early classification.
- To classify a sequence of observations, we then employ Bayesian inference to produce a posterior probability distribution over the set of class labels.
- We leverage this property in support of a variety of interpretability services, including explanation, counterfactual reasoning, verification of properties, and human modification.

Our implemented system, DISC, achieves similar performance to LSTMs and superior performance to HMMs and n-grams on a set of synthetic and real-world datasets, with the important advantage of being interpretable.

## Problem Set (Input, Output):

**Definition** 2.1 (Sequence Classification) Given a trace  $\tau$= ($\sigma_1$, $\sigma_2$, ... , $\sigma_n$), $\sigma_i \in \Sigma$ , where $\Sigma$ is a finite set of symbols, and C is a set of class labels, sequence classification is the task of predicting the class label $c \in C$ that corresponds to $\tau$ .

**Definition 2.2** DFA 

## Example

Example 2.1 (The office domain) 

Example 4.1

Example 4.2

Example 4.3

Example 4.4


## motivation

Our work shares some of its motivation with previous work that has proposed to learn interpretable classifiers which favour early prediction.

our work was originally motivated by the goal **recognition task**

Finally, it is worth mentioning that DFA learning has recently been used to learn high-level models of memories for RL agents. As such, our method might also provide interesting avenues for future work in reinforcement learning.

## challenge

### Challenge-I



### Challenge-II





## approach



### I

In this section, we described an approach to learning DFAs for sequence classification based on mixed integer linear programming.

### II

Mixed Integer Linear Programming (MILP) model

混合整数线性编程模型

PT（前缀树）

The main idea is to assign the DFA state reached by each node in the tree (which represents a sequence of observations).

主要思想是分配树中每个节点达到的DFA状态（代表一个观测序列）。

### III

Given a trace (or partial trace)  and the decisions of the one-vs-rest classifiers $\{D_c(\tau):c\in C\}$, we use an approximate Bayesian method to infer a posterior probability distribution over the true label c^*^.

我们使用近似贝叶斯方法来推断真实标签c上的后验概率分布。



## experiment



### Dataset



## References

Previous approaches to learning such automata have typically constructed the prefix tree from a set of traces and employed heuristic methods or SAT solvers to minimize the resulting automaton.

以前学习这种自动机的方法通常已经从一组迹线和使用的启发式方法或SAT求解器中构造了前缀树，以最大程度地减少所得的自动机。


### SOTA(State-Of-The-Art)

We now describe our Mixed Integer Linear Programming (MILP) model to learn DFAs. We rely on MILP solvers because they are **the state of the art** for solving a wide range of discrete optimization problems and they are guaranteed to find optimal solutions given sufficient resources (J ̈ unger et al. 2009).

## What-can-improve / What-didn’t-do

