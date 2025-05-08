---
title: "Vendor Scorecard | supplycm Algorithm Library"
description: "Plain-English explanation of vendor_scorecard from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, vendor_scorecard, supply chain, plain english, supplier & procurement"
---

# Vendor Scorecard

> **Call it:** `from supplycm.supplier import vendor_scorecard` · **Level:** Beginner · **You need:** basic arithmetic only

The weighted scorecard with ranking built in: suppliers, metrics, scores, weights - out come weighted totals and ranks. It is the quarterly review one-pager: who leads, who trails, and by how much on each metric.

**Think of it like this:** A league table for suppliers - same math every quarter, so movement up or down means something.

## When to reach for it

- Quarterly business reviews with suppliers
- Deciding which vendors earn more share of wallet

## Try it with supplycm

```python
from supplycm.supplier import vendor_scorecard

result = vendor_scorecard(['Alpha', 'Beta', 'Gamma'], ['quality', 'delivery'], [[90, 85], [80, 95], [70, 75]], [0.6, 0.4])
print(result)
```

You should see something like:

```text
{'Alpha': {'scores': {'quality': 90, 'delivery': 85}, 'total': 88.0, 'rank': 1}, 'Beta': {'scores': {'quality': 80, 'delivery': 95}, 'total': 86.0, 'rank': 2}, 'Gamma': {'scores': {'quality': 70, 'delivery': 75}, 'total': 72.0, 'rank': 3}}
```

Totals and ranks come back - Alpha edges Beta on the weighting used, Gamma trails clearly; the gap sizes matter as much as the order.

## Check yourself

1. What do the weights decide here?
2. Why publish the same scorecard every period?
3. A supplier ranks last but is your only source. Now what?

<details>
<summary>Show answers</summary>

1. How the trade-offs resolve - raise the delivery weight and Beta can overtake Alpha.

2. Trends beat snapshots - a supplier sliding from 88 to 81 is a conversation starter.

3. Scorecards inform, not decide: build an improvement plan (or a backup) rather than just dropping them.

</details>

## Try this now

Scorecard 3 real-or-invented vendors for two quarters; comment on the biggest mover and why.

---
[← Supplier Evaluation Matrix](supplier_evaluation_matrix.md) · [Back to Supplier & Procurement library](README.md) · [On-Time Delivery Rate →](on_time_delivery_rate.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
