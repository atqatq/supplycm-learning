---
title: "Northwest Corner Method | supplycm Algorithm Library"
description: "Plain-English explanation of northwest_corner_method from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, northwest_corner_method, supply chain, plain english, routing & transportation"
---

# Northwest Corner Method

> **Call it:** `from supplycm.routing import northwest_corner_method` · **Level:** Intermediate · **You need:** basic arithmetic only

The simplest start for shipping plans: fill the top-left cell as much as possible, move right or down, repeat. It ignores costs entirely - which is the point: it produces a fast, feasible starting plan that better methods then improve.

**Think of it like this:** Filling a form strictly left-to-right, top-to-bottom: no strategy, just a complete first draft to work from.

## When to reach for it

- Generating an initial feasible transportation plan
- Teaching the transportation simplex's first step

## Try it with supplycm

```python
from supplycm.routing import northwest_corner_method

result = northwest_corner_method(supply=[30, 50], demand=[20, 30, 30])
print(result)
```

You should see something like:

```text
[[20, 10, 0.0], [0.0, 20, 30]]
```

The allocation table - quantities ignoring cost; feed it to MODI and watch the improvement begin.

## Check yourself

1. Why use a method that ignores costs?
2. What are supply and demand here?
3. What comes immediately after?

<details>
<summary>Show answers</summary>

1. Speed to a FEASIBLE plan - the starting point's quality matters less than having one to optimize.

2. Warehouse capacities and customer requirements - the plan must drain supply into demand exactly.

3. Cost improvement (MODI / stepping-stone) - the draft's dumb allocations get traded toward cheap lanes.

</details>

## Try this now

Compute this plan's total cost; then compare with the least-cost plan - feel how much the improvement phase can win.

---
[← Hungarian Algorithm (Assignment)](assignment_problem_hungarian.md) · [Back to Routing & Transportation library](README.md) · [Least Cost Method →](least_cost_method.md)
