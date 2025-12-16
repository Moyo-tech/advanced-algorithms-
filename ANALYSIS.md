# Advanced Algorithms Project Analysis

## Overview

This repository contains two Jupyter notebooks demonstrating advanced algorithm design for real-world optimization problems. The work is from an academic assessment (GROUP28) focused on **Dynamic Programming**, **Graph Theory**, and **Combinatorial Optimization**.

---

## Notebook 1: Final_Summative_Assessment_.ipynb

### PART ONE: Resource Allocation & Task Assignment

**Problem Domain:** Campus Event Planning at ALU (African Leadership University)

**Tasks to Assign:**
- Receiving Guests
- Serving Refreshments
- Sitting Arrangements
- Campus Tour
- Entertaining Guests

**Volunteers:** Deogratias, Judith, Diane, John, Erastus

#### Algorithms & Techniques Used:

| Question | Problem Type | Algorithm | Key Technique |
|----------|--------------|-----------|---------------|
| Q1 | Simple Assignment | **Hopcroft-Karp** | Bipartite Maximum Matching |
| Q2 | Multi-task Assignment | **Ford-Fulkerson** | Maximum Flow Network |
| Q3 | Capacity-Constrained | **Maximum Matching** | Bipartite Graphs with Edge Weights |
| Q4 | Dual-Capacity | **Ford-Fulkerson** | Source-Sink Flow Network |
| Q5 | Multi-Session Tasks | **Maximum Flow** | Extended Flow Network |

**Key Insights:**
- Progressive problem complexity - each question adds a new constraint layer
- Dual-capacity modeling: volunteers have limits (max tasks) AND tasks have requirements (max volunteers)
- Results visualized using NetworkX bipartite graph plotting

---

### PART TWO: Traveling Salesman Problem (TSP)

**Problem:** Route optimization for a vehicle collecting materials from locations in Kigali, Rwanda:
- ALU (Starting Point)
- Kigali CBD
- Kanombe
- Kimironko
- Kaciru

**Algorithm:** Branch and Bound with **Memoization**

**Solution:**
- **Optimal Route:** ALU → Kaciru → Kigali CBD → Kimironko → Kanombe → ALU
- **Total Cost:** 34 units

---

## Notebook 2: GROUP28_Assessment5_Assignment3.ipynb

### Question 1: TSP for Delivery Routes

**Problem:** Find shortest delivery route across 5 city locations.

**Dual Implementation:**

| Approach | Time Complexity | Runtime (1000 iter) |
|----------|-----------------|---------------------|
| Naive (Brute Force) | O(N!) | ~0.021 seconds |
| Memoization (DP) | O(N² × 2^N) | ~0.078 seconds |

**Validation:** Tested on 3 different graph structures with consistent correct results.

---

### Question 2: Factorial Computation - DP Paradigm Comparison

**Head-to-head comparison** of Dynamic Programming paradigms:

| Approach | Type | Advantage | Limitation |
|----------|------|-----------|------------|
| **Memoization** | Top-Down | Fast for small n | RecursionError at n≥5000 |
| **Tabulation** | Bottom-Up | Handles large n | Slightly slower for small n |

**Key Discovery:** Tabulation wins for large-scale computation due to Python's recursion depth limit (~1000).

---

## Project Scenario: Campus Event Logistics Optimization System

### The Challenge

ALU is hosting a major campus event with two interconnected optimization problems:

1. **Human Resource Allocation:** Assign 5 volunteers to 5 tasks considering:
   - Individual capabilities and preferences
   - Maximum workload per volunteer
   - Minimum staffing requirements per task
   - Multi-session task support

2. **Logistics Route Optimization:** Collect materials from 5 Kigali locations with:
   - Single visit per location
   - Return to starting point
   - Minimum total travel cost

### Solution Approach

#### Phase 1: Task Assignment Evolution
1. **Baseline:** 1:1 matching with Hopcroft-Karp
2. **Capacity:** Added volunteer workload limits with Ford-Fulkerson
3. **Requirements:** Added edge capacities for task complexity
4. **Full Constraints:** Combined volunteer AND task capacities
5. **Multi-Session:** Extended for multiple time slots

#### Phase 2: Route Optimization
- Branch and Bound with Memoization
- Weighted graph model of Kigali
- Achieved optimal 34-unit cost route

#### Phase 3: Algorithm Paradigm Analysis
- Compared Naive O(N!) vs Memoized O(N² × 2^N) for TSP
- Analyzed Memoization vs Tabulation trade-offs

---

## What Makes This Project Stand Out

### 1. Progressive Complexity Design
Problems build incrementally - each question adds one constraint, making algorithmic choices clear.

### 2. Real-World Context
Uses actual Rwandan locations (Kimironko, Kanombe, Kaciru) and realistic event scenarios.

### 3. Multiple Algorithm Comparison
Compares approaches rather than just solving:
- Hopcroft-Karp vs Ford-Fulkerson
- Naive vs Memoized TSP
- Memoization vs Tabulation

### 4. Empirical Validation
Runtime benchmarks using `timeit` provide actual performance data.

### 5. Visualization
Consistent NetworkX/Matplotlib graphs make solutions interpretable.

### 6. Practical Limitations Discovery
Reveals Python's recursion depth limit - critical for production systems.

---

## Summary of Techniques & Methods

| Category | Techniques Used |
|----------|-----------------|
| **Graph Algorithms** | Bipartite Matching, Maximum Flow, Hopcroft-Karp, Ford-Fulkerson |
| **Optimization** | TSP, Branch and Bound, Greedy |
| **Dynamic Programming** | Memoization, Tabulation |
| **Data Structures** | Adjacency Matrices, Directed Graphs, Flow Networks |
| **Libraries** | NetworkX, Matplotlib, itertools, sys, timeit |
| **Analysis** | Time Complexity Analysis, Runtime Benchmarking |

---

## Files

- `Final_Summative_Assessment_.ipynb` - Task assignment & TSP solutions
- `GROUP28_Assessment5_Assignment3.ipynb` - TSP variants & factorial DP comparison
