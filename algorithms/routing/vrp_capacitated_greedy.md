---
title: "CVRP Greedy Insertion | supplycm Algorithm Library"
description: "Plain-English explanation of vrp_capacitated_greedy from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vrp_capacitated_greedy, supply chain, plain english, routing & transportation"
---

# CVRP Greedy Insertion

> **Call it:** `from supplycm.routing import vrp_capacitated_greedy` · **Level:** Intermediate · **You need:** basic arithmetic only

The workhorse vehicle routing start: each vehicle leaves the depot and repeatedly grabs the nearest customer that fits its remaining capacity; when nothing fits, it comes home and a new vehicle starts. Simple, fast, decent - the CVRP baseline.

**Think of it like this:** Loading delivery vans at dawn: each driver keeps picking nearby stops until the van is full, then returns for another round.

## When to reach for it

- Capacity-constrained delivery from one depot
- Seed routes before 2-opt or metaheuristic polish

## Try it with supplycm

```python
from supplycm.routing import vrp_capacitated_greedy

result = vrp_capacitated_greedy(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], demands=[0, 1, 1, 1], vehicle_capacity=2)
print(result)
```

You should see something like:

```text
[[0, 1, 3, 0], [0, 2, 0]]
```

Routes as customer lists per vehicle - check each respects capacity and covers everyone exactly once.

## Check yourself

1. What does 'capacitated' add over plain TSP?
2. Why does greedy leave money on the table?
3. What's the first polish to apply?

<details>
<summary>Show answers</summary>

1. Vehicles max out and return - the question splits from 'best tour' to 'best SET of tours under weight limits'.

2. It ignores route SHAPE and future customers - short-sighted grabs force long detours; improvement passes recover most of it.

3. Intra-route 2-opt per vehicle, then inter-route customer swaps - the standard one-two of VRP improvement.

</details>

## Try this now

Run with capacity 2 vs 3; compare route counts and totals, then 2-opt the longer route and quantify the fix.

---
[← Vehicle Scheduling (Minimum Fleet)](vehicle_scheduling.md) · [Back to Routing & Transportation library](README.md) · [Clarke-Wright Savings Algorithm →](vrp_savings.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
