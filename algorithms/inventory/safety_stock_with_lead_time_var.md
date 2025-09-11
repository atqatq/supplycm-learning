---
title: "Safety Stock with Lead Time Variability | supplycm Algorithm Library"
description: "Plain-English explanation of safety_stock_with_lead_time_var from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, safety_stock_with_lead_time_var, supply chain, plain english, inventory"
---

# Safety Stock with Lead Time Variability

> **Call it:** `from supplycm.inventory import safety_stock_with_lead_time_var` · **Level:** Advanced · **You need:** basic arithmetic only

Suppliers don't just deliver late sometimes - their DELIVERY TIME wobbles. This recipe adds that wobble: variability of demand AND of lead time both inflate the cushion. When a supplier's timing is unreliable, this is the honest version of safety stock.

**Think of it like this:** Planning airport arrival with both traffic variability AND security-line variability - the cushion must cover the worse of the two, sometimes both.

## When to reach for it

- Suppliers with erratic delivery performance
- Explaining WHY an unreliable supplier costs you real inventory money

## Try it with supplycm

```python
from supplycm.inventory import safety_stock_with_lead_time_var

result = safety_stock_with_lead_time_var(z=1.65, demand_mean=100, demand_std=10, lead_time_mean=8, lead_time_std=2)
print(result)
```

You should see something like:

```text
333.2837
```

A much larger cushion than stable-lead-time math would give - the lead-time wobble dominates, which is exactly the supplier's hidden cost.

## Check yourself

1. Which hurts more: demand wobble or lead-time wobble?
2. Supplier cuts lead-time std from 3 days to 1. Effect?
3. Why does lead-time variability scale with demand squared?

<details>
<summary>Show answers</summary>

1. Depends on sizes - but lead-time variance enters the formula amplified by demand squared; erratic suppliers are expensive.

2. Safety stock falls sharply - reliability improvements convert directly into inventory savings.

3. A long delay exposes MORE days of demand - the exposure compounds, not just adds.

</details>

## Try this now

Compute safety stock with lead_time_std 0 vs 3 for the same data; convert the difference into dollars at 25% holding.

---
[← Safety Stock (Normal Demand)](safety_stock_normal.md) · [Back to Inventory library](README.md) · [Demand During Lead Time →](demand_during_lead_time.md)
