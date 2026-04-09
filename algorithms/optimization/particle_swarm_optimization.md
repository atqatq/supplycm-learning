---
title: "Particle Swarm Optimization (PSO) | supplycm Algorithm Library"
description: "Plain-English explanation of particle_swarm_optimization from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, particle_swarm_optimization, supply chain, plain english, optimization"
---

# Particle Swarm Optimization (PSO)

> **Call it:** `from supplycm.optimization import particle_swarm_optimization` · **Level:** Advanced · **You need:** basic arithmetic only

A flock of candidate solutions flies through the search space: each particle remembers its personal best AND hears about the swarm's best, then blends momentum toward both. Social psychology as optimization - individuals balance pride, peer pressure, and inertia.

**Think of it like this:** A flock searching for food: each bird trusts its own best spot a little, follows the flock's champion a little, and keeps some momentum - the flock swirls toward abundance.

## When to reach for it

- Continuous parameter tuning (inventory levels, pricing knobs)
- Black-box objectives where gradients are unavailable

## Try it with supplycm

```python
from supplycm.optimization import particle_swarm_optimization

result = particle_swarm_optimization(objective=lambda x: (x[0] - 3) ** 2, bounds=[(0, 10)], num_particles=10, max_iter=30, seed=42)
print(result)
```

You should see something like:

```text
[[3.0004], 0.0]
```

The swarm's best position and score - particles balanced personal memory, social pull, and momentum to find the basin.

## Check yourself

1. What are the three forces on each particle?
2. PSO vs GA - contrast in one line?
3. When does the swarm underperform?

<details>
<summary>Show answers</summary>

1. Inertia (keep going), personal best (where I found food), social best (where the swarm found food) - the weights tune the culture.

2. PSO nudges continuous positions socially; GA recombines discrete structures genetically - flocking vs breeding.

3. Wildly multimodal spaces with weak communication - the flock camps on the first decent basin and misses better valleys.

</details>

## Try this now

Set the social weight to 0 and rerun - everyone optimizes alone; observe the cost of losing gossip.

---
[← Genetic Algorithm (GA)](genetic_algorithm.md) · [Back to Optimization library](README.md) · [Simulated Annealing (SA) →](simulated_annealing.md)
