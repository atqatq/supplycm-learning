---
title: "Transshipment Problem | supplycm Algorithm Library"
description: "Plain-English explanation of transshipment_problem from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, transshipment_problem, supply chain, plain english, routing & transportation"
---

# Transshipment Problem

> **Call it:** `from supplycm.routing import transshipment_problem` · **Level:** Advanced · **You need:** basic arithmetic only

Real networks have middlemen: goods flow factory -> depot -> store, with depots neither producing nor consuming. The transshipment problem optimizes flows through the entire chain, honoring every node's balance - supply, demand, or pass-through.

**Think of it like this:** Planning water through canals with junction reservoirs: sources pour in, cities drink, and every reservoir's inflow must equal its outflow plus what stays.

## When to reach for it

- Multi-echelon flow planning through DCs and hubs
- Any network where goods legitimately change vehicles mid-journey

## Try it with supplycm

```python
from supplycm.routing import transshipment_problem

result = transshipment_problem(supply=[20, 0], demand=[0, 20], transshipment_cost=[[0, 5, 3], [0, 0, 0], [0, 0, 0]])
print(result)
```

You should see something like:

```text
[[[0, 20], [0.0, 0.0]], 100.0]
```

The flow plan and total cost - watch goods route through the middle node when the two-hop path beats going direct.

## Check yourself

1. What distinguishes a transshipment node?
2. Why can a two-hop route beat a direct one?
3. How does this relate to min-cost flow?

<details>
<summary>Show answers</summary>

1. Pure pass-through: inflow equals outflow - it adds routing options, not supply or demand.

2. Economies, lane quality, or the direct lane being impossibly expensive - the model prices every option fairly.

3. It IS a min-cost flow with node balances - transshipment is the supply chain dialect of the same mathematics.

</details>

## Try this now

Make the direct lane expensive and the hub route cheap; verify flows reroute through the hub without breaking balances.

---
[← MODI / Transportation Simplex](transportation_simplex_modi.md) · [Back to Routing & Transportation library](README.md) · [Vehicle Scheduling (Minimum Fleet) →](vehicle_scheduling.md)
