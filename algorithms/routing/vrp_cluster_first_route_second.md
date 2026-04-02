---
title: "Cluster-First, Route-Second | supplycm Algorithm Library"
description: "Plain-English explanation of vrp_cluster_first_route_second from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vrp_cluster_first_route_second, supply chain, plain english, routing & transportation"
---

# Cluster-First, Route-Second

> **Call it:** `from supplycm.routing import vrp_cluster_first_route_second` · **Level:** Intermediate · **You need:** basic arithmetic only

The two-phase strategy in its purest form: first GROUP customers into vehicle-sized clusters (geographically), then solve a TSP within each cluster. Divide, then conquer - each phase stays simple, and the combination performs well.

**Think of it like this:** Organizing a school trip: form class groups first (clusters), then plan each group's museum route separately - no single mega-plan needed.

## When to reach for it

- Medium-sized CVRP instances needing structure
- Explaining VRP decomposition to non-specialists

## Try it with supplycm

```python
from supplycm.routing import vrp_cluster_first_route_second

result = vrp_cluster_first_route_second(customers=[(1, 1, 1), (2, 2, 1), (3, 1, 1)], depot=(0, 0), vehicle_capacity=5, k=2)
print(result)
```

You should see something like:

```text
[[0, 1, 2, 0], [0, 0, 0]]
```

Per-cluster routes - phase 1 drew the territories, phase 2 sequenced each territory's visits.

## Check yourself

1. What's the alternative to cluster-first-route-second?
2. Where does clustering fail the route?
3. How would you repair boundary mistakes?

<details>
<summary>Show answers</summary>

1. Route-first-cluster-second: build one giant tour, then split it into vehicle trips at depot returns.

2. Boundary customers - the wedge line puts a customer in cluster A while their best insertion is in B; interfaces leak efficiency.

3. Inter-route exchanges after routing - move a customer between clusters when the total drops; iteration fixes division errors.

</details>

## Try this now

Run it with k=2 and k=3; identify the boundary customer whose reassignment would clearly help.

---
[← VRP Sweep Algorithm](vrp_sweep.md) · [Back to Routing & Transportation library](README.md) · [Split Delivery VRP →](split_delivery_vrp.md)
