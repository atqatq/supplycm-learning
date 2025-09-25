---
title: "Weighted Average Cost | supplycm Algorithm Library"
description: "Plain-English explanation of weighted_average_cost from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, weighted_average_cost, supply chain, plain english, inventory"
---

# Weighted Average Cost

> **Call it:** `from supplycm.inventory import weighted_average_cost` · **Level:** Intermediate · **You need:** basic arithmetic only

Blend all cost layers into one average unit cost: total value divided by total units. Sales then carry that single average, no layer juggling. It smooths price swings - less dramatic than FIFO or LIFO, and pleasantly simple to explain.

**Think of it like this:** Your average fuel price across all fill-ups this quarter - one honest number for expense claims, no receipt archaeology.

## When to reach for it

- Commodities and bulk materials where layers are impractical
- Situations demanding simple, stable unit costing

## Try it with supplycm

```python
from supplycm.inventory import weighted_average_cost

result = weighted_average_cost(layers=[(100, 10.0), (300, 14.0)])
print(result)
```

You should see something like:

```text
13.0
```

13.0 per unit - the blend of the cheap and expensive layers; every sale and every remaining unit now carries that price.

## Check yourself

1. How does WAC behave in volatile price times?
2. What happens to the average after a very large expensive buy?
3. WAC vs FIFO for margin stability?

<details>
<summary>Show answers</summary>

1. It smooths - margins fluctuate less than FIFO/LIFO, and neither the oldest nor newest cost dominates.

2. It jumps toward the new cost - big receipts steer the average hard.

3. WAC wins on stability; FIFO wins on reflecting current replacement cost at the end of the period.

</details>

## Try this now

Blend layers [(200, 6), (100, 12), (100, 9)] into one WAC; then cost a 250-unit issue by hand and check.

---
[← LIFO Valuation](lifo_valuation.md) · [Back to Inventory library](README.md) · [Square Root Law of Inventory →](square_root_law.md)
