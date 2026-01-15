# NeuroCourier TSP – Ant Colony Optimization & Simulated Annealing

This project implements and compares two metaheuristics — **Ant Colony Optimization (ACO)** and **Simulated Annealing (SA)** — for the **metric Traveling Salesman Problem (TSP)**, framed as a logistics routing problem for a fictional start-up called *NeuroCourier*.

The goal is to generate good-quality tours quickly for instances with small, medium, and large numbers of cities and to study the trade-off between **solution quality** and **runtime**.

---

## 🔍 Problem

Given a set of cities and pairwise Euclidean distances, find a tour that:

- visits each city exactly once,
- returns to the starting city,
- has minimum total length.

This is an NP-hard problem (TSP), so we use metaheuristics instead of exact algorithms.

---

## 🧠 Implemented Algorithms

- **Ant Colony Optimization (ACO)**
  - Pheromone matrix on edges
  - Heuristic bias based on inverse distance
  - Evaporation + reinforcement using best tours
  - Tunable parameters: number of ants, α, β, evaporation rate ρ, iterations

- **Simulated Annealing (SA)**
  - State: permutation of cities (tour)
  - Neighbourhood: 2-opt / swap moves
  - Energy: tour length
  - Geometric cooling schedule with probabilistic acceptance of worse moves

---

## 📁 Project Structure

```text
.
├── aco.py         # ACO implementation for TSP
├── sa.py          # Simulated Annealing implementation for TSP
├── tsp_utils.py   # Utilities: instance generation, distance matrix, evaluation
├── experiments.py # Runs experiments for different instance sizes
├── plots.py       # Generates plots (tour length vs n, runtime vs n, etc.)
├── Plot.jpg       # Example result plot
└── README.md
