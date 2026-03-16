# Secure Dominating Set using Graph Neural Networks and Reinforcement Learning

## Overview

This project explores the **Secure Dominating Set (SDS)** problem in graphs using **Graph Neural Networks (GNNs)** combined with **Reinforcement Learning (Double Deep Q-Networks)**. The goal is to learn efficient strategies for selecting vertices that form a **minimum Secure Dominating Set**, ensuring both coverage and resilience in graph-based networks.

A motivating application is **smart urban safety**, where the algorithm can assist in determining optimal deployment locations for emergency services such as fire engines. The objective is to ensure that every region is covered while maintaining backup coverage in case of failures.

---

## Problem Statement

In graph theory:

* A **Dominating Set (DS)** is a subset of vertices such that every vertex in the graph is either in the set or adjacent to at least one vertex in the set.
* A **Secure Dominating Set (SDS)** adds an additional condition: for every vertex outside the dominating set, there exists a vertex in the set that can be replaced by it while still maintaining domination.

The SDS problem is **NP-hard**, meaning exact solutions become computationally infeasible for large graphs.

---

## Methodology

The proposed solution combines **deep learning and reinforcement learning techniques**:

* **Graph Neural Networks (GNNs)** are used to capture structural information of the graph.
* A **Message Passing Neural Network (MPNN)** framework is used to compute node embeddings.
* **Reinforcement Learning (Double Deep Q-Network)** is used to sequentially select vertices that form a Secure Dominating Set.
* A reward function guides the agent toward minimizing the SDS size while maintaining the security constraint.

The agent interacts with the graph environment, selecting vertices step-by-step until the graph becomes securely dominated.

---

## Training Setup

The model is trained on different graph families commonly used for evaluating graph algorithms:

* **Erdős–Rényi (ER) random graphs**
* **Barabási–Albert (BA) scale-free graphs**

Training configuration includes:

* Learning rate: `1e-4`
* Discount factor: `1.0`
* Replay buffer size: `500`
* Exploration rate gradually decays from `1.0` to `0.05`
* Larger graphs are trained for up to **800,000 episodes**.

---

## Results

The machine learning model was compared against heuristic algorithms for Secure Dominating Set construction.

Key observations:

* The ML model produces **smaller SDS sizes** compared to heuristics.
* Performance improves as graph size increases.
* The model demonstrates strong **scalability and generalization** across different graph families.

In several experiments, the model achieved **20–45% improvement** in SDS size compared to baseline heuristics.

---


## Technologies Used

* Python
* PyTorch
* NetworkX
* NumPy
* Matplotlib

---

## Applications

This approach can be applied to several real-world problems, including:

* Smart city infrastructure planning
* Emergency service deployment
* Network monitoring and security
* Sensor placement optimization
* Large-scale combinatorial optimization problems
