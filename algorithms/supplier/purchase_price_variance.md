---
title: "Purchase Price Variance | supplycm Algorithm Library"
description: "Plain-English explanation of purchase_price_variance from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, purchase_price_variance, supply chain, plain english, supplier & procurement"
---

# Purchase Price Variance

> **Call it:** `from supplycm.supplier import purchase_price_variance` · **Level:** Beginner · **You need:** basic arithmetic only

PPV multiplies the price gap (actual minus standard) by quantity bought: the money version of 'we paid more than planned'. It is the finance team's favorite procurement metric because it converts negotiation wins - and misses - straight into currency.

**Think of it like this:** Your monthly budget vs actual spending, times every purchase - small leaks become visible sums.

## When to reach for it

- Monthly reporting of sourcing performance to finance
- Catching silent price creep on long-running parts

## Try it with supplycm

```python
from supplycm.supplier import purchase_price_variance

result = purchase_price_variance(actual_price=10.5, standard_price=10.0, quantity=5000)
print(result)
```

You should see something like:

```text
2500.0
```

2,500 unfavorable - a 50-cent creep that nobody noticed unit by unit just became a five-figure annual story.

## Check yourself

1. What makes PPV 'unfavorable'?
2. Why can chasing PPV hurt quality?
3. Standard price is 10.0 and hasn't changed in 2 years. Risk?

<details>
<summary>Show answers</summary>

1. Actual price above standard - you paid more than the plan assumed.

2. Buyers squeeze price, suppliers quietly cheapen the product - total cost rises elsewhere.

3. The standard itself is stale; variances then measure inflation, not buyer skill - refresh the standards.

</details>

## Try this now

Compute PPV for +0.30 on 20,000 units; then argue both sides of celebrating a big favorable PPV.

---
[← Price Analysis](price_analysis.md) · [Back to Supplier & Procurement library](README.md) · [Spend Analysis →](spend_analysis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
