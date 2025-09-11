---
title: "Fill Rate Calculation | supplycm Algorithm Library"
description: "Plain-English explanation of fill_rate_calculation from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, fill_rate_calculation, supply chain, plain english, inventory"
---

# Fill Rate Calculation

> **Call it:** `from supplycm.inventory import fill_rate_calculation` · **Level:** Advanced · **You need:** basic arithmetic only

Fill rate measures the share of UNITS (not cycles) served from stock. It connects to safety stock through the expected shortage per cycle - a subtler but fairer lens than cycle service level, because one late cycle can mean one missed unit or ten thousand.

**Think of it like this:** Cycle service counts how often the bakery runs out; fill rate counts how many croissants customers actually got.

## When to reach for it

- Reporting customer-facing availability honestly
- Converting unit-based SLA promises into stock policies

## Try it with supplycm

```python
from supplycm.inventory import fill_rate_calculation

result = fill_rate_calculation(safety_stock=30, demand_std=12, lead_time=4, order_quantity=600)
print(result)
```

You should see something like:

```text
0.998
```

A high unit fill rate - big order quantities dilute each cycle's small expected shortage across many served units.

## Check yourself

1. Cycle service 95% can coexist with fill rate 99.5%. How?
2. What raises fill rate without touching safety stock?
3. Which metric should the sales contract specify?

<details>
<summary>Show answers</summary>

1. The 5% of cycles that stock out miss only a few units each - units smoothed the pain that cycles counted.

2. Bigger order quantities - fewer cycles, each shortage spread over more units.

3. Fill rate - customers feel units, not cycles; just be ready to compute it honestly.

</details>

## Try this now

Hold safety stock fixed and compare fill rate at order quantities 200 vs 1200 - explain the intuition.

---
[← Cycle Service Level from Safety Stock](cycle_service_level.md) · [Back to Inventory library](README.md) · [Expected Backorder Units →](expected_backorder.md)
