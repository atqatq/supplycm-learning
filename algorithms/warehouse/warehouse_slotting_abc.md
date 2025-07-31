---
title: "Warehouse Slotting (ABC) | supplycm Algorithm Library"
description: "Plain-English explanation of warehouse_slotting_abc from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, warehouse_slotting_abc, supply chain, plain english, warehouse"
---

# Warehouse Slotting (ABC)

> **Call it:** `from supplycm.warehouse import warehouse_slotting_abc` · **Level:** Beginner · **You need:** basic arithmetic only

Put your fastest movers in the easiest spots. This assigns items to zones by their pick frequency: A items get the golden zone near shipping, C items go to the far shelves. Travel is usually half of picking cost, and slotting is the cheapest way to shrink it.

**Think of it like this:** A supermarket puts milk and bread at the back so you walk past everything - warehouses do the OPPOSITE: bestsellers up front.

## When to reach for it

- Re-slotting a warehouse that has 'just grown organically' over years
- After a demand shift: what was an A item last year may be a C now

## Try it with supplycm

```python
from supplycm.warehouse import warehouse_slotting_abc

result = warehouse_slotting_abc(items=[('mugs', 40.0, 1200.0), ('espresso-machine', 8.0, 60.0), ('cups', 35.0, 900.0)], num_zones=3)
print(result)
```

You should see something like:

```text
[['mugs', 0], ['cups', 1], ['espresso-machine', 2]]
```

Each item gets a zone number - zone 0 is prime real estate; your hottest items should own it.

## Check yourself

1. What data decides an item's zone?
2. How often should you re-slot?
3. Why does slotting beat 'work faster' as a lever?

<details>
<summary>Show answers</summary>

1. Pick frequency (demand) - and often weight/size too, since heavy items also want easy spots.

2. At least seasonally - demand shifts silently turn your layout stale.

3. Cutting travel attacks most of the picking time; you cannot motivation your way out of a bad layout.

</details>

## Try this now

Slot 6 items of your choice into 2 zones; compute roughly what share of picks now live in the front zone.

---
[Back to Warehouse library](README.md) · [Warehouse Layout Optimization →](warehouse_layout_optimization.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
