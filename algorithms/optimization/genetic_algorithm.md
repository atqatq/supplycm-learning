---
title: "Genetic Algorithm (GA) | supplycm Algorithm Library"
description: "Plain-English explanation of genetic_algorithm from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, genetic_algorithm, supply chain, plain english, optimization"
---

# Genetic Algorithm (GA)

> **Call it:** `from supplycm.optimization import genetic_algorithm` · **Level:** Advanced · **You need:** basic arithmetic only

Evolution as an algorithm: a population of candidate solutions breeds - the fittest become parents, children mix their traits (crossover) and mutate - and generations roll forward toward better answers. No gradient needed, just a fitness score and patience.

**Think of it like this:** Breeding roses: no botanist 'computes' the perfect rose - they select, cross, and let generations accumulate improvement.

## When to reach for it

- Messy search spaces where gradients don't exist
- Design problems (schedules, layouts) with mixable building blocks

## Try it with supplycm

```python
from supplycm.optimization import genetic_algorithm

result = genetic_algorithm(fitness=lambda x: -((x[0] - 3) ** 2), bounds=[(0, 10)], pop_size=20, generations=30, seed=42)
print(result)
```

You should see something like:

```text
[[3.4399], -0.1935]
```

The best individual and its fitness - generations of selection and mutation pulled the population toward the optimum.

## Check yourself

1. What role does mutation play?
2. Why 'no gradient needed' matters?
3. What's the classic tuning failure?

<details>
<summary>Show answers</summary>

1. Fresh genes: without it, the population inbreeds and stalls on early luck - mutation keeps exploration alive.

2. Many real objectives are bumpy, discrete, or simulation-based - evolution only asks 'better or worse', never 'which slope'.

3. Selection pressure too strong - the population converges prematurely on a mediocre peak; diversity is fuel, spend it wisely.

</details>

## Try this now

Run with mutation_rate 0.01 vs 0.3; compare final fitness and discuss the exploration-exploitation balance.

---
[← Ant Colony Optimization (ACO)](ant_colony_optimization.md) · [Back to Optimization library](README.md) · [Particle Swarm Optimization (PSO) →](particle_swarm_optimization.md)
