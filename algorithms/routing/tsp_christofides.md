---
title: "TSP Christofides Algorithm | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_christofides from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_christofides, supply chain, plain english, routing & transportation"
---

# TSP Christofides Algorithm

> **Call it:** `from supplycm.routing import tsp_christofides` · **Level:** Advanced · **You need:** basic arithmetic only

The most beautiful guarantee in routing: build a minimum spanning tree, fix its odd-degree cities with a minimum matching, and turn the result into a tour. On triangle-inequality distances the tour is provably within 50% of optimal - certainty, not just hope.

**Think of it like this:** A bridge engineer's promise: build this specific design and, whatever the terrain, the bridge holds at least this much load - a warranty, not a hope.

## When to reach for it

- Distance-matrix routing where guarantees matter
- Strong baseline construction for metric TSP

## Try it with supplycm

```python
from supplycm.routing import tsp_christofides

result = tsp_christofides(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]])
print(result)
```

You should see something like:

```text
[[0, 1, 3, 2, 0], 80]
```

A tour with its length - on real road-like distances it typically lands far better than its 1.5x worst-case promise.

## Check yourself

1. What is the 1.5x guarantee?
2. Why does the spanning tree start the construction?
3. What breaks the guarantee?

<details>
<summary>Show answers</summary>

1. Tour length at most 1.5 times optimal - proven, always, when distances obey the triangle inequality.

2. It's the cheapest skeleton connecting everyone - Christofides then patches the skeleton into a full loop cheaply.

3. Non-metric distances - if the triangle inequality fails, the proof's floor falls away too.

</details>

## Try this now

Run Christofides and Held-Karp on the same 8-city metric instance; express the tour as a percentage of optimal.

---
[← TSP Held-Karp (Exact)](tsp_held_karp.md) · [Back to Routing & Transportation library](README.md) · [Hungarian Algorithm (Assignment) →](assignment_problem_hungarian.md)
