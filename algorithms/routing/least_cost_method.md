---
title: "Least Cost Method | supplycm Algorithm Library"
description: "Plain-English explanation of least_cost_method from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, least_cost_method, supply chain, plain english, routing & transportation"
---

# Least Cost Method

> **Call it:** `from supplycm.routing import least_cost_method` · **Level:** Intermediate · **You need:** basic arithmetic only

A smarter transportation start: allocate to the CHEAPEST available lane first, then the next cheapest, until supply meets demand. Still just a starting plan - but a far better-informed one than northwest corner, so the improvement phase starts closer to done.

**Think of it like this:** Booking hotel blocks for a wedding: grab the cheapest acceptable venues first, then fill the leftovers - the initial plan already shows taste.

## When to reach for it

- Better initial solutions for transportation problems
- When the starting plan itself must be presentable

## Try it with supplycm

```python
from supplycm.routing import least_cost_method

result = least_cost_method(supply=[30, 50], demand=[20, 30, 30], costs=[[8, 6, 10], [9, 12, 13]])
print(result)
```

You should see something like:

```text
[[0.0, 30, 0.0], [20, 0.0, 30]]
```

The allocation table - cheap lanes (cost 6, then 8...) filled first; compare its total cost with northwest corner's.

## Check yourself

1. How much better is least-cost vs northwest corner?
2. Can the greedy start still be beaten?
3. When is the starting method irrelevant?

<details>
<summary>Show answers</summary>

1. Usually substantially - greedy-on-cost starts near-optimal on easy instances, saving improvement iterations.

2. Easily - filling one cheap lane can strand an expensive corner; optimizers exist precisely because greed misleads.

3. When MODI runs to full optimality anyway - the endpoint is identical, only the journey differs.

</details>

## Try this now

Compute both methods' starting costs on the same problem; then find the truly optimal plan by trial and see who was closer.

---
[← Northwest Corner Method](northwest_corner_method.md) · [Back to Routing & Transportation library](README.md) · [Vogel's Approximation Method (VAM) →](vogels_approximation.md)
