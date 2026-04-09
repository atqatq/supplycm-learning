---
title: "Ant Colony Optimization (ACO) | supplycm Algorithm Library"
description: "Plain-English explanation of ant_colony_optimization from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, ant_colony_optimization, supply chain, plain english, optimization"
---

# Ant Colony Optimization (ACO)

> **Call it:** `from supplycm.optimization import ant_colony_optimization` · **Level:** Advanced · **You need:** basic arithmetic only

Digital ants lay pheromone on routes they walk; better (shorter) routes get walked more, reinforced more, and eventually the colony converges on strong paths. Population-based search that turns 'good experiences leave traces' into an optimization engine.

**Think of it like this:** Ants finding your picnic: no ant knows the map, but the shortest trail ends up smelling strongest - the colony's shared memory does the planning.

## When to reach for it

- Routing and sequencing problems with many local traps
- Problems where good solutions share reusable building blocks

## Try it with supplycm

```python
from supplycm.optimization import ant_colony_optimization

result = ant_colony_optimization(distances=[[0, 1, 2], [1, 0, 1], [2, 1, 0]], num_ants=5, iterations=10, seed=42)
print(result)
```

You should see something like:

```text
[[0, 1, 2, 0], 4]
```

The converged route and its length - the pheromone trail quietly concentrated on the strongest ordering.

## Check yourself

1. What do pheromones encode?
2. Why does evaporation matter?
3. ACO vs simulated annealing - different how?

<details>
<summary>Show answers</summary>

1. Collective memory: trails that led to short tours get reinforced, making them more tempting to future ants.

2. It forgets stale wisdom - without evaporation, early bad trails haunt the colony forever.

3. Colony memory vs single-walker temperature: ACO learns a DISTRIBUTION over routes; SA explores alone with cooling luck.

</details>

## Try this now

Run with evaporation 0.1 vs 0.9; watch convergence speed and stability change, and explain the role of forgetting.

---
[← N-Queens Backtracking](n_queens_backtracking.md) · [Back to Optimization library](README.md) · [Genetic Algorithm (GA) →](genetic_algorithm.md)
