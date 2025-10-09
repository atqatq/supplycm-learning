---
title: "Periodic Review (R, S) Policy | supplycm Algorithm Library"
description: "Plain-English explanation of periodic_review_policy from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, periodic_review_policy, supply chain, plain english, inventory"
---

# Periodic Review (R, S) Policy

> **Call it:** `from supplycm.inventory import periodic_review_policy` · **Level:** Intermediate · **You need:** basic arithmetic only

Check inventory on a SCHEDULE (every Friday, every month) and order up to level S. No continuous watching - the calendar does the work. The order-up-to level must cover the review period PLUS lead time of demand, which makes it bigger than continuous-review equivalents.

**Think of it like this:** Visiting grandma every Sunday with her pantry topped up to the same shelf line - the visit is fixed, the top-up flexes.

## When to reach for it

- Supplier deliver on fixed schedules (weekly routes)
- Situations where ordering discipline beats micro-optimization

## Try it with supplycm

```python
from supplycm.inventory import periodic_review_policy

result = periodic_review_policy(demand_rate=20, review_period=7, lead_time=3, ordering_cost=50, holding_cost=0.5, z_score=1.65, demand_std=8)
print(result)
```

You should see something like:

```text
[7, 241.7421, 304.9876]
```

Returns the order-up-to level S (and target) - notice it covers 10 days of demand (7 review + 3 lead), not 3.

## Check yourself

1. Why must S cover review period + lead time?
2. When is periodic review worth its bigger buffer?
3. What happens to orders in quiet weeks?

<details>
<summary>Show answers</summary>

1. An order placed Friday serves the following Friday-plus-lead-time - the gap between checks is exposed too.

2. When suppliers deliver on schedules or checking stock continuously is impractical - rhythm has real value.

3. You may order little or nothing - the top-up logic self-throttles; the schedule never changes.

</details>

## Try this now

Halve the review period on the example and quantify how S shrinks - then argue whether weekly checks are worth it.

---
[← Fixed Order Quantity Lot Sizing](fixed_order_quantity.md) · [Back to Inventory library](README.md) · [(R, Q) Continuous Review Policy →](r_q_policy.md)
