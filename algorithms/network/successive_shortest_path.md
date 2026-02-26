---
title: "Successive Shortest Path (Min-Cost Flow) | supplycm Algorithm Library"
description: "Plain-English explanation of successive_shortest_path from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, successive_shortest_path, supply chain, plain english, networks"
---

# Successive Shortest Path (Min-Cost Flow)

> **Call it:** `from supplycm.network import successive_shortest_path` · **Level:** Advanced · **You need:** basic arithmetic only

The elegant min-cost builder: repeatedly send flow along the CHEAPEST available path (respecting reduced costs), one unit-batch at a time, until demand is met. Built cheap first, so the result is optimal by construction - no loops to cancel later.

**Think of it like this:** Booking a fully-loaded flight plan always on the cheapest available connection first - by the time the last passenger is placed, no cheaper arrangement exists.

## When to reach for it

- Building optimal shipping plans from scratch
- Min-cost flow when you want optimality without repair passes

## Try it with supplycm

```python
from supplycm.network import successive_shortest_path

result = successive_shortest_path(capacity=[[0, 2, 2, 0], [0, 0, 0, 2], [0, 0, 0, 2], [0, 0, 0, 0]], costs=[[0, 1, 3, 0], [0, 0, 0, 1], [0, 0, 0, 1], [0, 0, 0, 0]], supply=[2, 0, 0, -2])
print(result)
```

You should see something like:

```text
4.0
```

The optimal cost - identical to cycle-canceling's answer, reached by construction instead of correction.

## Check yourself

1. Why does 'cheapest path first' yield a global optimum?
2. Cycle canceling vs successive shortest path - style difference?
3. What practical inputs must be honest here?

<details>
<summary>Show answers</summary>

1. Reduced costs keep every future choice honest - each batch extends the optimal solution rather than spoiling it.

2. Fix-then-fix vs build-right-the-first-time - same optimum, opposite workflows.

3. Capacities, lane costs, and supplies - the model optimizes exactly what you encode; sloppy costs give confidently wrong plans.

</details>

## Try this now

Raise one lane's cost mid-plan and rerun; trace how the flow reroutes before concluding anything about lane pricing.

---
[← Min-Cost Flow (Cycle Canceling)](min_cost_flow_cycle_canceling.md) · [Back to Networks library](README.md)
