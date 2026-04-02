---
title: "Multi-Depot VRP | supplycm Algorithm Library"
description: "Plain-English explanation of multi_depot_vrp from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, multi_depot_vrp, supply chain, plain english, routing & transportation"
---

# Multi-Depot VRP

> **Call it:** `from supplycm.routing import multi_depot_vrp` · **Level:** Advanced · **You need:** basic arithmetic only

Several depots, one customer set: which depot serves whom, and in what order? This assigns customers to depots and builds routes - the two decisions that single-depot VRP never faced. Get the assignment right and the routes almost plan themselves.

**Think of it like this:** Three fire stations covering a city: each alarm goes to the nearest capable station - draw the territories well and response times fall.

## When to reach for it

- Regional DCs each serving overlapping customer areas
- Fleets based at multiple yards

## Try it with supplycm

```python
from supplycm.routing import multi_depot_vrp

result = multi_depot_vrp(customers=[(1, 1, 1), (2, 2, 1)], depots=[(0, 0), (5, 5)], vehicle_capacity=5)
print(result)
```

You should see something like:

```text
[[-1, 0, 1]]
```

Routes grouped by depot - each customer rides from its assigned base; nudge a customer and watch them switch depots.

## Check yourself

1. What does the depot assignment decision trade off?
2. How does this interact with network design?
3. What's the classic failure mode?

<details>
<summary>Show answers</summary>

1. Distance to customers versus depot workload balance - nearest isn't always right when capacities strain.

2. It's the tactical twin: strategic siting chooses depots; this assigns flows daily - the layers nest.

3. Territory drawn by geography alone ignores demand volume - one depot drowns while its neighbor idles; balance assignments, not just maps.

</details>

## Try this now

Add a customer equidistant from both depots; decide their assignment by workload, then verify with the function.

---
[← VRP with Time Windows](vrp_with_time_windows.md) · [Back to Routing & Transportation library](README.md) · [Periodic VRP →](periodic_vrp.md)
