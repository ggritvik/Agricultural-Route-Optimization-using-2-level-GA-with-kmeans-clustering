# Agricultural-Route-Optimization-using-2-level-GA-with-kmeans-clustering


Welcome to this comprehensive Traveling Salesman Problem (TSP) optimization notebook. This project contains multiple implementations ranging from simple heuristics for small datasets to advanced clustered and hybrid meta-heuristic genetic algorithms (GAs) for large-scale and constrained routing challenges.

Link to Colab File : https://colab.research.google.com/drive/1zEiBA27gl6Uzpd1PkadksfzIk3uTjSiY?usp=sharing

---

## 📋 Project Overview & Datasets

This notebook demonstrates solutions across three different scales of complexity:

1. **Small Dataset (`small.csv`)**
   * **Scale:** 31 Nodes
   * **Approach:** Nearest Neighbor Heuristic
   * **Objective:** Quick initialization and baseline route plotting.

2. **Medium Dataset (`medium.csv`)**
   * **Scale:** 100 Nodes
   * **Approaches:** Epochal Random Search, K-Means Clustering + Intra-cluster Brute Force, and Clustered Two-Level Genetic Algorithm (GA).

3. **Large / Constrained Datasets (`large.csv` / `City_Nodes.csv`)**
   * **Scale:** Up to 1000 Nodes
   * **Approaches:** DBSCAN Density Clustering + Degree-Constrained Sparse Graphs, K-Means Soft Clustering, Constraint-aware 2-Opt Refinement, and Multi-Objective (Distance & Time) Bi-Level Genetic Algorithms.

---

## 🛠️ Implemented Algorithms & Key Features

### 1. Nearest Neighbor Heuristic
* Fast greedy initialization used for small scale analysis.
* Computes Euclidean transitions on 2D coordinates.

### 2. K-Means & DBSCAN Clustered TSP
* Divides large datasets into compact geographic regions.
* Solves smaller sub-problems to maintain computational scalability.
* Uses **DBSCAN** for outlier identification (noise management) and **K-Means** for spatial alignment.

### 3. Bi-Level Genetic Algorithm (Two-Level GA)
* **Intra-Cluster Optimization:** Uses custom Ordered Crossover (OX) and mutation operators to solve regional routing paths.
* **Inter-Cluster Optimization:** Optimizes the transition sequence between cluster gateways to minimize global transit distances.

### 4. Degree-Constrained Road Networks & Constraints
* Builds undirected degree-constrained suburban graphs to model physical routing.
* Supports hard-pass-through intermediate node constraints with on-the-fly path repair operators.
* Employs multi-objective optimization balancing **Distance (km)** and **Travel Time (hours)**.

---

## 📊 Optimization Results Summary

| Dataset | Algorithm | Total Distance (Units/km) | Key Visual Features |
| :--- | :--- | :--- | :--- |
| **Small** | Nearest Neighbor Heuristic | ~66.79 | Baseline single salesman tour |
| **Medium** | Epochal Search | ~38.75 | Basic evolutionary improvement |
| **Medium** | K-Means + Centroid TSP | ~15.57 | Regional clustering optimization |
| **Medium** | Two-Level GA | **9.71** | Highly optimized cluster gateways |
| **Large** | Two-Level GA (28 Clusters) | **43.08** | Advanced segmented gateway path |
| **Constrained** | C2 Soft-Clustering + Multi-Obj GA | **70.76** | Constraint repaired open routing tour |

---

## 📦 Required Libraries

To run all the modules successfully, the following libraries are installed or imported within the Colab environment:
* `pygad` (Genetic Algorithms)
* `scikit-learn` (K-Means, DBSCAN, NearestNeighbors)
* `matplotlib` & `seaborn` (Static Plotting)
* `scipy` (Sparse Graph Computations)
* `pandas` & `numpy` (Data Processing)
