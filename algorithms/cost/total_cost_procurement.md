---
title: "Total Procurement Cost | supplycm Algorithm Library"
description: "Plain-English explanation of total_cost_procurement from the supplycm Costing module, with a runnable Python example and self-check questions."
keywords: "supplycm, cost, total_cost_procurement, supply chain, plain english, costing"
---

# Total Procurement Cost

> **Call it:** `from supplycm.cost import total_cost_procurement` · **Level:** Beginner · **You need:** basic arithmetic only

Beyond the purchase itself, procurement piles up ordering costs, holding costs, stockout costs, quality failures, and admin. This function adds all six buckets into one total, so a 'cheaper' supplier with more defects and delays can be exposed for what it truly costs.

**Think of it like this:** A car's true yearly cost: not just the price tag, but fuel, insurance, parking, repairs, and your time.

## When to reach for it

- Supplier selection where quality and reliability differ
- Budgeting the full cost of a sourcing decision

## Try it with supplycm

```python
from supplycm.cost import total_cost_procurement

result = total_cost_procurement(purchase_cost=100000, ordering_cost=5000, holding_cost=12000, stockout_cost=8000, quality_cost=6000, admin_cost=2000)
print(result)
```

You should see something like:

```text
133000
```

The total lands well above the purchase price - the 'extras' add about a third, and two of them (stockouts, defects) are pure pain you can negotiate away.

## Check yourself

1. Name the six cost buckets in the function.
2. Supplier B is 3% cheaper but doubles defect costs. How do you decide?
3. Which bucket shrinks when you order in bigger, rarer batches?

<details>
<summary>Show answers</summary>

1. Purchase, ordering, holding, stockout, quality, admin.

2. Sum total cost for both - the defect line usually eats the 3% and more.

3. Ordering - but holding grows; that tension is exactly what EOQ balances.

</details>

## Try this now

Cost out two invented suppliers with different price/defect/delay profiles and crown the true winner on total cost.

---
[← Landed Cost](landed_cost.md) · [Back to Costing library](README.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
