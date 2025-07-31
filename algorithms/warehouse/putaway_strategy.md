---
title: "Putaway Strategy | supplycm Algorithm Library"
description: "Plain-English explanation of putaway_strategy from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, putaway_strategy, supply chain, plain english, warehouse"
---

# Putaway Strategy

> **Call it:** `from supplycm.warehouse import putaway_strategy` · **Level:** Intermediate · **You need:** basic arithmetic only

Putaway decides WHERE an inbound item goes - and a good rule sends it straight to its proper home by class and size, no wandering. This assigns each item to a fitting slot by volume and ABC class, so receiving decides once and picking benefits all week.

**Think of it like this:** A tidy kitchen: flour goes to the flour shelf every time - nobody searches, nobody blocks the aisle 'just for now'.

## When to reach for it

- Reducing 'drop it anywhere' chaos after receiving
- Mixed warehouses where size and class both matter

## Try it with supplycm

```python
from supplycm.warehouse import putaway_strategy

result = putaway_strategy(items=[('A', 'A', 5.0, 100.0), ('B', 'B', 10.0, 20.0), ('C', 'C', 25.0, 5.0)], slots=[('S1', 10.0), ('S2', 20.0), ('S3', 30.0)])
print(result)
```

You should see something like:

```text
{'A': 'S1', 'B': 'S2', 'C': 'S3'}
```

Each item gets a slot ID that fits its volume and class - fast small items to easy slots, bulky slow ones to roomy ones.

## Check yourself

1. Why does bad putaway slow down PICKING later?
2. What does 'directed putaway' add over free putaway?
3. When would you knowingly put a fast item in a bad slot?

<details>
<summary>Show answers</summary>

1. Because pickers pay for the random choice every time - putaway errors tax every future pick.

2. A system decision instead of a forklift operator's guess - consistency, and slot data you can trust.

3. Rarely - e.g., to consolidate a product family or respect weight limits; the point is deciding consciously.

</details>

## Try this now

Assign 5 mixed items (different volumes, classes) to 3 slots by hand, then check the function agrees.

---
[← Warehouse Layout Optimization](warehouse_layout_optimization.md) · [Back to Warehouse library](README.md) · [Order Picking Wave Planning →](order_picking_wave.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
