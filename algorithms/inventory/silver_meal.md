---
title: "Silver-Meal Heuristic | supplycm Algorithm Library"
description: "Plain-English explanation of silver_meal from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, silver_meal, supply chain, plain english, inventory"
---

# Silver-Meal Heuristic

> **Call it:** `from supplycm.inventory import silver_meal` · **Level:** Advanced · **You need:** basic arithmetic only

A clever compromise between L4L and big batches: keep EXTENDING one order to cover more future periods while the average cost PER PERIOD keeps falling, and stop the moment it rises. Fast, intuitive, and usually within a few percent of the perfect answer.

**Think of it like this:** Carpooling decisions: add a passenger while the average cost per person drops; when a fourth rider would raise it, the car leaves.

## When to reach for it

- Dynamic demand where fixed lot sizes misfit
- A defensible, near-optimal rule you can explain in one minute

## Try it with supplycm

```python
from supplycm.inventory import silver_meal

result = silver_meal(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 2], 120.0]
```

The chosen order periods and total cost - watch it bundle the first periods together, then start a new order when averaging turns against it.

## Check yourself

1. What exactly is being minimized period by period?
2. Why stop when the average starts rising?
3. Silver-Meal vs Wagner-Whitin - trade-off?

<details>
<summary>Show answers</summary>

1. Average cost per period covered: setup plus accumulated holding, divided by periods served.

2. Adding another period now adds more holding than the setup saving spreads - the trend never comes back.

3. Wagner-Whitin is exactly optimal but heavier and opaque; Silver-Meal is near-optimal, fast, and explainable.

</details>

## Try this now

Trace by hand why the heuristic stops extending at period 3 for [20, 20, 20, 60] with setup 80, holding 2.

---
[← Lot-for-Lot (L4L)](lot_for_lot.md) · [Back to Inventory library](README.md) · [Least Unit Cost Heuristic →](least_unit_cost.md)
