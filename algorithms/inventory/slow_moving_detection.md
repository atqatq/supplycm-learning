---
title: "Slow-Moving Item Detection | supplycm Algorithm Library"
description: "Plain-English explanation of slow_moving_detection from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, slow_moving_detection, supply chain, plain english, inventory"
---

# Slow-Moving Item Detection

> **Call it:** `from supplycm.inventory import slow_moving_detection` · **Level:** Intermediate · **You need:** basic arithmetic only

One step before dead: slow movers still sell, but too slowly to justify their stock. This compares each item's sales pace against a threshold and flags the laggards. Catching items while they are SLOW (not dead) preserves most of their value.

**Think of it like this:** A gym member who comes once a month: not yet a lost cause, but the renewal conversation should start now.

## When to reach for it

- Monthly inventory hygiene before items decay into dead stock
- Rebalancing buy budgets from laggards to winners

## Try it with supplycm

```python
from supplycm.inventory import slow_moving_detection

result = slow_moving_detection(items=[('gloves', 300.0, 8.0), ('scarf', 400.0, 2.0), ('beanie', 250.0, 30.0)], slow_threshold=0.2)
print(result)
```

You should see something like:

```text
[['gloves', False], ['scarf', False], ['beanie', False]]
```

The scarf flags as slow - a 0.005 turnover pace vs the threshold; gloves and beanie are healthy.

## Check yourself

1. Slow vs dead - where's the line?
2. What counts as an acceptable pace?
3. A slow mover is a deliberate loss leader. Keep?

<details>
<summary>Show answers</summary>

1. Slow still sells below an acceptable pace; dead does not sell at all. Slow is where intervention pays best.

2. Items per period relative to stock and class norms - the threshold encodes your patience policy.

3. Yes - but track it knowingly with the cost visible, not inside an unexamined pile.

</details>

## Try this now

Detect slow movers among 8 items; propose one concrete action per flagged item and estimate the cash freed.

---
[← Dead Stock Identification](dead_stock_identification.md) · [Back to Inventory library](README.md) · [Obsolescence Cost →](obsolescence_cost.md)
