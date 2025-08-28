---
title: "Master Production Schedule (MPS) | supplycm Algorithm Library"
description: "Plain-English explanation of master_production_schedule from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, master_production_schedule, supply chain, plain english, mrp & production planning"
---

# Master Production Schedule (MPS)

> **Call it:** `from supplycm.mrp import master_production_schedule` · **Level:** Intermediate · **You need:** basic arithmetic only

The MPS is the promise the factory makes: how many to build each period after real orders consume the forecast. Forecast minus actual orders leaves what still needs producing, in lot-size chunks. It is the bridge between sales plans and shop-floor reality.

**Think of it like this:** A bakery's baking plan: the morning forecast minus the walk-in orders already placed - whatever remains is what the ovens must cover.

## When to reach for it

- Setting weekly production quantities for end items
- Checking whether demand is cannibalizing the forecast (order burn-down)

## Try it with supplycm

```python
from supplycm.mrp import master_production_schedule

result = master_production_schedule(forecast=[10, 20, 30, 40], actual_orders=[5, 10, 15, 20], on_hand=10, lot_size=50, planning_horizon=4)
print(result)
```

You should see something like:

```text
[0.0, 50, 0.0, 50]
```

Build quantities per period - note how they only appear where remaining demand (plus inventory effects) actually forces a lot to be built.

## Check yourself

1. What does 'consuming the forecast' mean?
2. Orders exceed forecast in a period - what does MPS do?
3. Why produce in lot sizes inside MPS?

<details>
<summary>Show answers</summary>

1. Real orders replace forecasted demand line by line, so production plans real remaining need, not forecast plus orders double-counted.

2. The forecast is fully consumed and the excess pulls production or inventory forward - watch the on-hand row.

3. Real ovens, machines, and setups come in economical chunks - lot sizing turns continuous need into buildable batches.

</details>

## Try this now

Set on_hand=0, lot_size=25 and trace period by period why each build happens when it does.

---
[← MRP Calculation](mrp_calculation.md) · [Back to MRP & Production Planning library](README.md) · [Available-to-Promise (ATP) →](available_to_promise.md)
