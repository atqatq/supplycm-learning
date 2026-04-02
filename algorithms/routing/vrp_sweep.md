---
title: "VRP Sweep Algorithm | supplycm Algorithm Library"
description: "Plain-English explanation of vrp_sweep from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vrp_sweep, supply chain, plain english, routing & transportation"
---

# VRP Sweep Algorithm

> **Call it:** `from supplycm.routing import vrp_sweep` · **Level:** Intermediate · **You need:** basic arithmetic only

Stir the customer map like a clock hand from the depot: customers are swept into wedges, each wedge becomes one vehicle's route. Geography does the clustering - nearby angular neighbors ride together, then each wedge is routed TSP-style.

**Think of it like this:** Cutting a pizza into wedges: each slice is one vehicle's territory - everyone in a slice is close together, so the route within flows naturally.

## When to reach for it

- Radially distributed customers around a depot
- Fast territory design before detailed routing

## Try it with supplycm

```python
from supplycm.routing import vrp_sweep

result = vrp_sweep(customers=[(1, 1, 1), (2, 2, 1), (3, 1, 1)], depot=(0, 0), vehicle_capacity=5)
print(result)
```

You should see something like:

```text
[[2, 0, 1]]
```

Routes per wedge - each holds angular neighbors; redraw the sweep line and the territories reshuffle.

## Check yourself

1. What does the sweep angle decide?
2. When does sweep clustering mislead?
3. How do you pick the number of wedges?

<details>
<summary>Show answers</summary>

1. Cluster membership - customers within a wedge travel together; bad angles split natural neighbors across routes.

2. When distance isn't angular - customers at similar angles but very different radii get lumped despite being far apart.

3. Total demand divided by vehicle capacity, adjusted for geography - then let the routing math judge the result.

</details>

## Try this now

Sweep 8 customers with two different starting angles; compare the resulting route sets and their totals.

---
[← Clarke-Wright Savings Algorithm](vrp_savings.md) · [Back to Routing & Transportation library](README.md) · [Cluster-First, Route-Second →](vrp_cluster_first_route_second.md)
