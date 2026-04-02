---
title: "Chinese Postman Problem | supplycm Algorithm Library"
description: "Plain-English explanation of chinese_postman from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, chinese_postman, supply chain, plain english, routing & transportation"
---

# Chinese Postman Problem

> **Call it:** `from supplycm.routing import chinese_postman` · **Level:** Advanced · **You need:** basic arithmetic only

Cover every street of a network at minimum total distance - repeating where necessary. If the network is Eulerian, no repeats are needed; otherwise, find the cheapest set of edge-doublings that fixes the odd nodes. Route inspection, solved exactly.

**Think of it like this:** The postal carrier's perfect day: every street served once, with the unavoidable repeats planned on the shortest detours - not discovered mid-round.

## When to reach for it

- Mail, meter reading, street sweeping, gritting routes
- Any job priced by EDGE coverage, not stop visits

## Try it with supplycm

```python
from supplycm.routing import chinese_postman

result = chinese_postman(adjacency={0: [(1, 2), (2, 2)], 1: [(0, 2), (2, 3)], 2: [(0, 2), (1, 3)]})
print(result)
```

You should see something like:

```text
[[0, 2, 1, 0], 7.0]
```

The closed route and its total length - on this all-even network, zero repeats were needed; try an odd network and watch repeats appear.

## Check yourself

1. When does the postman need to repeat streets?
2. How are odd nodes 'fixed'?
3. Why 'Chinese' postman?

<details>
<summary>Show answers</summary>

1. When odd-degree nodes exist - pairing them with cheapest detours restores the even structure repeats buy.

2. Minimum-weight matching pairs them up; each pair's connecting path gets duplicated - the cheapest legal patch.

3. Named for the 1962 paper by Chinese mathematician Mei-Ko Kwan studying a postman's route in Beijing - mathematics remembering its origins.

</details>

## Try this now

Give one node degree 3, rerun, and identify which street the postman now walks twice and why that was the cheapest fix.

---
[← Eulerian Tour](eulerian_tour.md) · [Back to Routing & Transportation library](README.md) · [Rural Postman Problem →](rural_postman.md)
