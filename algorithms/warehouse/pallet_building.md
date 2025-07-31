---
title: "Pallet Building | supplycm Algorithm Library"
description: "Plain-English explanation of pallet_building from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, pallet_building, supply chain, plain english, warehouse"
---

# Pallet Building

> **Call it:** `from supplycm.warehouse import pallet_building` · **Level:** Intermediate · **You need:** basic arithmetic only

Decides which cartons go on which pallet so loads are stable and trucks carry fewer pallets. This function packs items by volume using a first-fit-decreasing approach: biggest boxes first, then fill the gaps. Fewer, denser pallets mean fewer trailers and lower freight bills.

**Think of it like this:** Packing a car trunk for vacation: big suitcases first, soft bags filling the gaps - done badly, you make two trips.

## When to reach for it

- Consolidating orders onto the fewest pallets
- Checking whether mixed orders can share a pallet safely

## Try it with supplycm

```python
from supplycm.warehouse import pallet_building

result = pallet_building(items=[(1.0, 1.0, 1.0), (2.0, 2.0, 2.0), (1.0, 1.0, 1.0), (1.5, 1.0, 1.0)], pallet_capacity=8.0)
print(result)
```

You should see something like:

```text
[[1], [3, 0, 2]]
```

Pallets come back as lists of item indices - watch how the big carton leads and small ones fill around it.

## Check yourself

1. Why place the biggest items first?
2. Volume packing ignores what real-world constraints?
3. How does pallet building cut freight cost?

<details>
<summary>Show answers</summary>

1. Small items fit almost anywhere; big items fit almost nowhere - placing them first avoids stranded space.

2. Weight limits, stacking strength, fragility, and orientation - all matter before a pallet ships.

3. Fewer pallets per order can mean fewer trucks, or better use of a trailer's floor positions.

</details>

## Try this now

Pack 6 boxes (two big, four small) into a 10-unit pallet by hand, then verify with the function.

---
[← TSP-Based Picking](traveling_salesman_picking.md) · [Back to Warehouse library](README.md) · [Dock Door Assignment →](dock_door_assignment.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
