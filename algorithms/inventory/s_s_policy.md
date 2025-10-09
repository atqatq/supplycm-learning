---
title: "(s, S) Min-Max Policy | supplycm Algorithm Library"
description: "Plain-English explanation of s_s_policy from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, s_s_policy, supply chain, plain english, inventory"
---

# (s, S) Min-Max Policy

> **Call it:** `from supplycm.inventory import s_s_policy` · **Level:** Advanced · **You need:** basic arithmetic only

A twist on (R, Q): when stock hits the minimum s, order enough to reach the MAXIMUM S - so order sizes FLEX with how far you've fallen. It blends the simplicity of thresholds with top-up logic, common in min-max ERP settings and retail replenishment.

**Think of it like this:** A phone plan: below 10% battery you charge, but you always charge to 100% - however empty it was.

## When to reach for it

- ERP min-max replenishment setups
- Variable demands where fixed Q wastes or starves

## Try it with supplycm

```python
from supplycm.inventory import s_s_policy

result = s_s_policy(demand_rate=20, lead_time=3, ordering_cost=50, holding_cost=0.5, z_score=1.65, demand_std=8)
print(result)
```

You should see something like:

```text
[82.8631, 146.1086]
```

Returns s (trigger) and S (target) - orders will top up to S whatever the shortfall, so quiet periods order small and busy ones order big.

## Check yourself

1. How does the order size differ from (R, Q)?
2. What's the advantage of variable order sizes?
3. When does (s, S) beat (R, Q) clearly?

<details>
<summary>Show answers</summary>

1. It varies: the order is S minus current position, not a fixed Q.

2. They match the actual shortfall - fewer oversize deliveries in slow periods, better coverage after surges.

3. Lumpy demand with expensive setups - big top-ups after surges avoid the multiple small orders a fixed Q would force.

</details>

## Try this now

Simulate two weeks of spiky demand by hand under (s, S) and note how order sizes vary while (R, Q) would not.

---
[← (R, Q) Continuous Review Policy](r_q_policy.md) · [Back to Inventory library](README.md) · [Base-Stock (Order-Up-To) Policy →](base_stock_policy.md)
