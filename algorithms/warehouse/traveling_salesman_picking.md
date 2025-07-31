---
title: "TSP-Based Picking | supplycm Algorithm Library"
description: "Plain-English explanation of traveling_salesman_picking from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, traveling_salesman_picking, supply chain, plain english, warehouse"
---

# TSP-Based Picking

> **Call it:** `from supplycm.warehouse import traveling_salesman_picking` · **Level:** Advanced · **You need:** basic arithmetic only

Treats picking as the Traveling Salesman Problem: visit every pick location with the shortest possible walk. For small orders (a handful of picks) the math is quick and beats fixed patterns like S-shape by real distances. For huge orders, heuristics keep it fast.

**Think of it like this:** Errand day with 6 stops: the shortest loop saves real time versus visiting them in the order you remembered them.

## When to reach for it

- Small multi-line orders where travel dominates
- Calculating the true lower bound when evaluating simpler routing rules

## Try it with supplycm

```python
from supplycm.warehouse import traveling_salesman_picking

result = traveling_salesman_picking(pick_locations=[(2, 1), (5, 3), (1, 4), (6, 2)])
print(result)
```

You should see something like:

```text
[0, 2, 1, 3]
```

The visit order minimizes total walking for these exact coordinates - compare it to a naive order to see the savings.

## Check yourself

1. Why not always use TSP routing in warehouses?
2. S-shape vs TSP on a 30-line order - practical winner?
3. What data makes TSP picking accurate?

<details>
<summary>Show answers</summary>

1. Aisles constrain movement (you cannot walk through shelves) - coordinates must model the real walkable network.

2. Often similar distance, but S-shape wins on simplicity and consistency; TSP shines on small, spread-out picks.

3. True travel distances between locations (or a good aisle-graph model), not straight-line guesses.

</details>

## Try this now

Plot 5 pick points on grid paper, find the shortest loop by eye, then verify with the function.

---
[← Return (Back-and-Forth) Routing](return_routing.md) · [Back to Warehouse library](README.md) · [Pallet Building →](pallet_building.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
