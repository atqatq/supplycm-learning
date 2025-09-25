---
title: "Dead Stock Identification | supplycm Algorithm Library"
description: "Plain-English explanation of dead_stock_identification from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, dead_stock_identification, supply chain, plain english, inventory"
---

# Dead Stock Identification

> **Call it:** `from supplycm.inventory import dead_stock_identification` · **Level:** Intermediate · **You need:** basic arithmetic only

Dead stock is inventory with zero movement over a window - the function flags items whose recent periods show no sales at all. Dead stock is not just storage cost; it is cash wearing a costume, and every month it sits, it gets harder to recover.

**Think of it like this:** A gym membership nobody uses: paid for, occupying space, delivering nothing - cancel or repurpose it.

## When to reach for it

- Quarterly cleanups before clearance campaigns
- Freeing warehouse slots and cash for items that actually sell

## Try it with supplycm

```python
from supplycm.inventory import dead_stock_identification

result = dead_stock_identification(items=[('leg-warmer', [0, 0, 0, 0, 0, 0]), ('sneaker', [3, 0, 4, 0, 2, 1]), ('fanny-pack', [0, 0, 0, 0, 1, 0])], periods=6)
print(result)
```

You should see something like:

```text
[['leg-warmer', True], ['sneaker', False], ['fanny-pack', False]]
```

The leg-warmers flag as dead - six periods of silence; the fanny-pack survives on one sale but is on notice.

## Check yourself

1. How many quiet periods before calling something dead?
2. Dead but strategic (service part for sold machines). Keep?
3. First move for newly flagged dead stock?

<details>
<summary>Show answers</summary>

1. Policy choice - many firms use 6-12 months; seasonal items need windows that respect their season.

2. Sometimes - that is a conscious decision with carrying cost acknowledged, not an accident.

3. Check data errors (wrong location, unrecorded sales), then discount, bundle, donate, or return to supplier - in that order of speed.

</details>

## Try this now

Flag dead items in a 12-item invented history; design the clearance sequence that recovers the most cash.

---
[← Inventory Aging Schedule](aging_schedule.md) · [Back to Inventory library](README.md) · [Slow-Moving Item Detection →](slow_moving_detection.md)
