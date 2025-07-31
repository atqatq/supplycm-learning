---
title: "Order Picking Wave Planning | supplycm Algorithm Library"
description: "Plain-English explanation of order_picking_wave from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, order_picking_wave, supply chain, plain english, warehouse"
---

# Order Picking Wave Planning

> **Call it:** `from supplycm.warehouse import order_picking_wave` · **Level:** Intermediate · **You need:** basic arithmetic only

Waves group orders into batches released together, so pickers, packers, and docks work in a steady rhythm instead of chaos. This spreads orders across a chosen number of waves to balance the work. Fewer, bigger waves are efficient but late orders wait; more waves react faster but lose batching.

**Think of it like this:** Baking cookies in batches by oven capacity - you could bake one cookie at a time, but you would live in the kitchen.

## When to reach for it

- Planning release schedules for a shift's orders
- Balancing picker workload across the day

## Try it with supplycm

```python
from supplycm.warehouse import order_picking_wave

result = order_picking_wave(orders=[[1, 2], [3], [4, 5, 6], [7, 8]], num_waves=2)
print(result)
```

You should see something like:

```text
[[2, 1], [0, 3]]
```

Two wave lists come back, each holding several orders - count the lines per wave to see whether the workload is balanced.

## Check yourself

1. What trades off when you choose fewer waves?
2. How do carrier cutoff times shape wave planning?
3. When does wave picking lose to zone or batch picking?

<details>
<summary>Show answers</summary>

1. Efficiency (batching, less travel) vs responsiveness - late-arriving orders wait for the next release.

2. Waves must finish before each carrier leaves - the schedule is built backwards from the trucks.

3. When orders are tiny and urgent all day - continuous release keeps service snappier.

</details>

## Try this now

Split 12 varied orders into 3 waves by hand (aim for equal lines), then compare with the function's split.

---
[← Putaway Strategy](putaway_strategy.md) · [Back to Warehouse library](README.md) · [S-Shape (Serpentine) Picking Route →](s_shape_routing.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
