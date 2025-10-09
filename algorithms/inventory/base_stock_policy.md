---
title: "Base-Stock (Order-Up-To) Policy | supplycm Algorithm Library"
description: "Plain-English explanation of base_stock_policy from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, base_stock_policy, supply chain, plain english, inventory"
---

# Base-Stock (Order-Up-To) Policy

> **Call it:** `from supplycm.inventory import base_stock_policy` · **Level:** Intermediate · **You need:** basic arithmetic only

The purest top-up rule: keep inventory POSITION at a base-stock level S - every demand unit triggers an order for one unit. No batch logic, no thresholds: the pipeline mirrors demand. In its pure form it minimizes delays for items where ordering cost per unit is negligible.

**Think of it like this:** A relay runner: one runner leaves exactly when one arrives - the team on the track is always the same size.

## When to reach for it

- Cheap-to-order items (digital ordering, drop-ship)
- Understanding the skeleton inside every other policy

## Try it with supplycm

```python
from supplycm.inventory import base_stock_policy

result = base_stock_policy(demand_rate=100, lead_time=2, review_period=1, z_score=1.96, demand_std=10)
print(result)
```

You should see something like:

```text
333.9482
```

The base-stock level S - expected demand over lead time plus review window, dressed with a 95% safety cushion.

## Check yourself

1. What makes base-stock 'pure'?
2. Why does S cover lead time PLUS review period?
3. Base-stock vs (R, S) periodic - relationship?

<details>
<summary>Show answers</summary>

1. Every unit sold is replaced - order quantity always equals the demand seen since the last check.

2. Between checks nothing can be ordered - the exposure window is the sum, and S must survive it.

3. Identical top-up logic; base-stock is the idea, (R, S) is its scheduled implementation.

</details>

## Try this now

Raise review_period from 1 to 7 and explain the jump in S to a store manager in plain words.

---
[← (s, S) Min-Max Policy](s_s_policy.md) · [Back to Inventory library](README.md) · [Joint Replenishment →](joint_replenishment.md)
