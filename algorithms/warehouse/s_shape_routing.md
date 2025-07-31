---
title: "S-Shape (Serpentine) Picking Route | supplycm Algorithm Library"
description: "Plain-English explanation of s_shape_routing from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, s_shape_routing, supply chain, plain english, warehouse"
---

# S-Shape (Serpentine) Picking Route

> **Call it:** `from supplycm.warehouse import s_shape_routing` · **Level:** Intermediate · **You need:** basic arithmetic only

The S-shape is the classic warehouse walking route: enter an aisle, traverse it fully, loop to the next - like mowing a lawn in stripes. It is simple to teach, impossible to get lost, and usually within a short distance of the optimal tour.

**Think of it like this:** Mowing the lawn in neat stripes: you never recut grass, you never skip a patch, and you end where the mower parks.

## When to reach for it

- Picker training - the default route everyone can follow
- Warehouses with mostly full-aisle picks (you would cross most aisles anyway)

## Try it with supplycm

```python
from supplycm.warehouse import s_shape_routing

result = s_shape_routing(pick_aisles=[1, 3, 4, 6])
print(result)
```

You should see something like:

```text
[1, 3, 4, 6, 4, 3, 1]
```

The route visits aisles in order, traversing each fully - predictable, teachable, and no backtracking within aisles.

## Check yourself

1. When does S-shape waste distance?
2. Name two alternatives to S-shape.
3. Why is simple routing often best in practice?

<details>
<summary>Show answers</summary>

1. When an aisle has just one pick at its entrance - you still walk the whole aisle.

2. Return routing (go in and come back the same aisle) and midpoint routing (turn at half-aisle).

3. Pickers follow it without thinking, errors drop, and the distance gap to 'optimal' is usually small.

</details>

## Try this now

A picker needs items in aisles 1, 2, 5, 7. Sketch the S-route, mark where it hurts (sparse aisle 5), and estimate the extra distance.

---
[← Order Picking Wave Planning](order_picking_wave.md) · [Back to Warehouse library](README.md) · [Return (Back-and-Forth) Routing →](return_routing.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
