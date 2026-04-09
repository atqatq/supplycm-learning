---
title: "Simulated Annealing (SA) | supplycm Algorithm Library"
description: "Plain-English explanation of simulated_annealing from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, simulated_annealing, supply chain, plain english, optimization"
---

# Simulated Annealing (SA)

> **Call it:** `from supplycm.optimization import simulated_annealing` · **Level:** Advanced · **You need:** basic arithmetic only

Accept better moves always; occasionally accept WORSE ones early (high temperature) so the search can escape traps, then cool down and grow conservative. The metallurgy metaphor is real: controlled cooling settles atoms - or schedules - into low-energy states.

**Think of it like this:** Shaking a bumpy tray of marbles hard at first so they escape small dips, then gently - finally each marble rests in a deep valley, not the first dent.

## When to reach for it

- Escaping local optima on bumpy objective landscapes
- Sequencing and layout problems with decent local moves

## Try it with supplycm

```python
from supplycm.optimization import simulated_annealing

result = simulated_annealing(objective=lambda x: (x[0] - 3) ** 2, initial=[0.0], neighbor=lambda x, rng: [x[0] + rng.uniform(-1, 1)], max_iter=200, seed=42)
print(result)
```

You should see something like:

```text
[[2.9983], 0.0]
```

The final solution near the optimum - early hot steps wandered freely; the cooling schedule gradually locked the search onto the valley.

## Check yourself

1. Why accept worse moves at all?
2. What does the cooling schedule control?
3. SA vs tabu search - the philosophical difference?

<details>
<summary>Show answers</summary>

1. Escapology: strict improvement gets trapped at the first local optimum; temporary worse moves are the ticket over the ridge.

2. The patience curve - how long the search stays adventurous before committing; too fast freezes into poor basins.

3. SA explores downhill via temperature luck; tabu remembers and forbids - randomness vs memory as the escape mechanism.

</details>

## Try this now

Cool 10x faster and compare final quality; then slow it 10x and watch the time-quality trade-off appear.

---
[← Particle Swarm Optimization (PSO)](particle_swarm_optimization.md) · [Back to Optimization library](README.md) · [Tabu Search →](tabu_search.md)
