---
title: "Ford-Fulkerson Max Flow | supplycm Algorithm Library"
description: "Plain-English explanation of ford_fulkerson_max_flow from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, ford_fulkerson_max_flow, supply chain, plain english, networks"
---

# Ford-Fulkerson Max Flow

> **Call it:** `from supplycm.network import ford_fulkerson_max_flow` · **Level:** Advanced · **You need:** basic arithmetic only

How much can flow from source to sink at once? Ford-Fulkerson keeps finding paths with spare capacity ('augmenting paths') and pushes flow along them until no path remains. The total pushed is the network's maximum throughput - the capacity of the whole system.

**Think of it like this:** Filling a highway system: keep routing trucks along any route with spare lanes until every route is jammed - the total moving is the max flow.

## When to reach for it

- Pipeline, port, or network throughput limits
- Sizing how much demand a logistics network can absorb

## Try it with supplycm

```python
from supplycm.network import ford_fulkerson_max_flow

result = ford_fulkerson_max_flow(capacity=[[0, 5, 0, 0], [0, 0, 4, 3], [0, 0, 0, 2], [0, 0, 0, 0]], source=0, sink=3)
print(result)
```

You should see something like:

```text
5.0
```

The maximum flow value - trace where it splits across the two middle lanes; the bottleneck decides everything.

## Check yourself

1. What is an 'augmenting path'?
2. What limits max flow?
3. How is this a supply chain question?

<details>
<summary>Show answers</summary>

1. Any source-to-sink route with unused capacity remaining - each one found adds flow until none survive.

2. The narrowest cut of the network - total flow equals the smallest set of lanes whose removal disconnects source from sink.

3. It's literally 'how much can we ship per period through this network?' - capacity planning in one number.

</details>

## Try this now

Bump one bottleneck lane's capacity and re-run; identify the next bottleneck that immediately appears.

---
[← Prim's Minimum Spanning Tree](prim_mst.md) · [Back to Networks library](README.md) · [Edmonds-Karp Max Flow →](edmonds_karp_max_flow.md)
