---
title: "(R, Q) Continuous Review Policy | supplycm Algorithm Library"
description: "Plain-English explanation of r_q_policy from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, r_q_policy, supply chain, plain english, inventory"
---

# (R, Q) Continuous Review Policy

> **Call it:** `from supplycm.inventory import r_q_policy` · **Level:** Intermediate · **You need:** basic arithmetic only

The classic pair: when inventory position hits reorder point R, order a fixed quantity Q. Stock is watched CONTINUOUSLY, orders fire exactly when needed, and every order is the same comfortable size. It is the workhorse policy behind most ERP min-max logic.

**Think of it like this:** A vending machine that calls its supplier the moment slot sales reach a level, always restocking the same case count.

## When to reach for it

- High-value items worth monitoring continuously
- Systems where consistent order sizes simplify receiving and transport

## Try it with supplycm

```python
from supplycm.inventory import r_q_policy

result = r_q_policy(demand_rate=20, lead_time=3, ordering_cost=50, holding_cost=0.5, z_score=1.65, demand_std=8)
print(result)
```

You should see something like:

```text
[82.8631, 63.2456]
```

Returns R and Q - R guards the lead-time window with safety stock; Q balances ordering against holding, EOQ-style.

## Check yourself

1. What does each letter control?
2. Continuous vs periodic review - which holds less stock?
3. Why can two items with identical demand get different Qs?

<details>
<summary>Show answers</summary>

1. R: WHEN to order (position threshold); Q: HOW MUCH to order (economic quantity).

2. Continuous - it reacts instantly, so it needs a smaller buffer for the same service.

3. Costs differ - ordering and holding parameters drive Q; demand only anchors R's exposure window.

</details>

## Try this now

Recompute with demand_std=0 and see R collapse to pure lead-time demand - explain why the cushion vanished.

---
[← Periodic Review (R, S) Policy](periodic_review_policy.md) · [Back to Inventory library](README.md) · [(s, S) Min-Max Policy →](s_s_policy.md)
