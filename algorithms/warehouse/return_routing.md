---
title: "Return (Back-and-Forth) Routing | supplycm Algorithm Library"
description: "Plain-English explanation of return_routing from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, return_routing, supply chain, plain english, warehouse"
---

# Return (Back-and-Forth) Routing

> **Call it:** `from supplycm.warehouse import return_routing` · **Level:** Intermediate · **You need:** basic arithmetic only

Return routing sends the picker INTO an aisle and back out the same way - no crossing to the far end. For aisles where picks cluster near the entrance, this beats walking the full S-loop. The trick is knowing when each style wins.

**Think of it like this:** Checking mailboxes in one apartment building - you go in, walk to the far box, and come back the same corridor; no need to exit the other side.

## When to reach for it

- Sparse picks deep in short aisles
- Mixed routes where most picks sit near the aisle entrance

## Try it with supplycm

```python
from supplycm.warehouse import return_routing

result = return_routing(pick_aisles=[(1, 0.2, 0.8), (2, 0.1, 0.3), (4, 0.3, 0.9)])
print(result)
```

You should see something like:

```text
[1, 2, 4, 2, 1]
```

The route returns in visit order - each aisle is entered and exited from the same end, skipping the far walk entirely.

## Check yourself

1. When does return routing beat S-shape?
2. What does the position data in the example represent?
3. Can you mix return and S-shape on one route?

<details>
<summary>Show answers</summary>

1. When picks sit near the aisle's near end - the far-end walk would be wasted distance.

2. Where along the aisle each pick sits - depth matters as much as which aisle.

3. Yes - smart pickers switch per aisle based on where the picks sit inside it.

</details>

## Try this now

For one aisle with picks at 10%, 20%, and 90% depth, compare return vs S-shape distance by sketching both.

---
[← S-Shape (Serpentine) Picking Route](s_shape_routing.md) · [Back to Warehouse library](README.md) · [TSP-Based Picking →](traveling_salesman_picking.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
