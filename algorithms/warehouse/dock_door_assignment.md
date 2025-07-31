---
title: "Dock Door Assignment | supplycm Algorithm Library"
description: "Plain-English explanation of dock_door_assignment from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, dock_door_assignment, supply chain, plain english, warehouse"
---

# Dock Door Assignment

> **Call it:** `from supplycm.warehouse import dock_door_assignment` · **Level:** Intermediate · **You need:** basic arithmetic only

Which trailer parks at which door matters more than it looks: grouping same-destination trailers onto neighboring doors keeps forklifts short and staging lanes unblocked. This assigns trailers to doors grouped by destination - one small decision that speeds up every load.

**Think of it like this:** Airport gates: flights to the same region cluster in one pier, so passengers and bags walk less.

## When to reach for it

- Busy docks where destinations mix and forklifts crisscross
- Reducing staging-lane collisions between outbound destinations

## Try it with supplycm

```python
from supplycm.warehouse import dock_door_assignment

result = dock_door_assignment(trailers=[('T1', 'NYC'), ('T2', 'LA'), ('T3', 'NYC'), ('T4', 'LA'), ('T5', 'Chicago')], num_doors=3)
print(result)
```

You should see something like:

```text
{'door_0': ['T1', 'T3'], 'door_1': ['T2', 'T4'], 'door_2': ['T5']}
```

Each destination gets a door (or shares one) - NYC loads at one door, LA at another, and forklifts stop crossing the yard.

## Check yourself

1. Why group by destination?
2. More doors than destinations - assign freely or reserve?
3. What breaks good door plans?

<details>
<summary>Show answers</summary>

1. One destination per area means one staging lane, one pickup, no sorting errors at the last minute.

2. Reserve by flow: the busiest destinations earn the doors nearest shipping and staging.

3. Volume shifts by season - re-check assignments when destinations or volumes change materially.

</details>

## Try this now

Assign 8 trailers (3 destinations) to 4 doors by hand with the 'group by destination' rule; where does the rule strain?

---
[← Pallet Building](pallet_building.md) · [Back to Warehouse library](README.md) · [Cross-Dock Scheduling →](cross_dock_scheduling.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
