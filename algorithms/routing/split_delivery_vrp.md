---
title: "Split Delivery VRP | supplycm Algorithm Library"
description: "Plain-English explanation of split_delivery_vrp from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, split_delivery_vrp, supply chain, plain english, routing & transportation"
---

# Split Delivery VRP

> **Call it:** `from supplycm.routing import split_delivery_vrp` · **Level:** Advanced · **You need:** basic arithmetic only

Classic VRP forces each customer onto exactly ONE vehicle - but why? Allowing a customer's demand to be SPLIT across vehicles can serve everyone with fewer trucks and fewer kilometers. This computes routes where quantities may divide.

**Think of it like this:** Moving day: one giant sofa needs two movers - insisting one person carry everything alone wastes the team's capacity.

## When to reach for it

- Big customers whose demand dwarfs vehicle slack
- Dense urban delivery where flexibility beats purity

## Try it with supplycm

```python
from supplycm.routing import split_delivery_vrp

result = split_delivery_vrp(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], demands=[0, 2, 2, 2], vehicle_capacity=3)
print(result)
```

You should see something like:

```text
[[[0, 1, 3, 0], [0.0, 2, 0.0, 1]], [[0, 2, 3, 0], [0.0, 0.0, 2, 1]]]
```

Routes with per-stop delivered quantities - one customer's 2 units arriving as 1+1 is legal here, and that freedom shrinks the fleet.

## Check yourself

1. Why does splitting reduce vehicle count?
2. What's the operational cost of splitting?
3. When is splitting most valuable?

<details>
<summary>Show answers</summary>

1. It eliminates stranded capacity - trucks no longer return half-full just because one customer 'belonged' elsewhere.

2. Extra stops at the same address, split paperwork, and customer confusion - model the benefit against the friction.

3. When demands hover near capacity - the awkward remainders that force extra vehicles vanish when division is allowed.

</details>

## Try this now

Compare vehicle counts with and without splitting at demands [0,3,3,2] capacity 4; quantify the saved truck.

---
[← Cluster-First, Route-Second](vrp_cluster_first_route_second.md) · [Back to Routing & Transportation library](README.md) · [VRP with Time Windows →](vrp_with_time_windows.md)
