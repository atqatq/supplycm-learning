---
title: "Composite Supplier Rating | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_rating from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_rating, supply chain, plain english, supplier & procurement"
---

# Composite Supplier Rating

> **Call it:** `from supplycm.supplier import supplier_rating` · **Level:** Beginner · **You need:** basic arithmetic only

One number to summarize a supplier: scores per dimension (quality, delivery, price...) combined with weights into a single rating. Use it as the headline of a monthly report - with the dimension scores always shown underneath, never alone.

**Think of it like this:** A hotel's overall star rating - useful at a glance, but you read the sub-scores (cleanliness, location) before booking.

## When to reach for it

- Monthly supplier summaries for management
- Comparing many suppliers on one consistent scale

## Try it with supplycm

```python
from supplycm.supplier import supplier_rating

result = supplier_rating(scores={'quality': 90, 'delivery': 85, 'price': 80}, weights={'quality': 0.4, 'delivery': 0.3, 'price': 0.3})
print(result)
```

You should see something like:

```text
85.5
```

About 85.5 overall - strong quality pulling up an average price score; the trend matters more than one month's value.

## Check yourself

1. Why never report the single rating alone?
2. Quality 0.6 vs 0.4 weight - who wins the argument?
3. Rating slipped from 88 to 84. Next step?

<details>
<summary>Show answers</summary>

1. An 85 can hide a failing dimension - always show component scores so problems stay visible.

2. Whoever can justify the weight with business impact - weights are policy, not math.

3. Open the dimensions, find the mover, and ask the supplier for a corrective plan - before the trend settles.

</details>

## Try this now

Rate two suppliers on 4 dimensions, then find the weight change that would flip the ranking - and decide if that weight is defensible.

---
[← Supplier Audit Score](supplier_audit_score.md) · [Back to Supplier & Procurement library](README.md) · [Supplier Risk Score →](supplier_risk_score.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
