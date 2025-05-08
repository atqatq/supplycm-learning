---
title: "Spend Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of spend_analysis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, spend_analysis, supply chain, plain english, supplier & procurement"
---

# Spend Analysis

> **Call it:** `from supplycm.supplier import spend_analysis` · **Level:** Beginner · **You need:** basic arithmetic only

Rolls up every transaction into spend by category and by supplier, then shows concentration: how much goes to each supplier within each category. It is the first step of every sourcing strategy - you cannot negotiate what you cannot see.

**Think of it like this:** A bank statement for purchasing: categories, merchants, and the one subscription quietly eating your budget.

## When to reach for it

- Finding consolidation opportunities (many suppliers, one category)
- Preparing category strategies and savings targets

## Try it with supplycm

```python
from supplycm.supplier import spend_analysis

result = spend_analysis([('IT', 'VendorX', 40000), ('IT', 'VendorY', 15000), ('Logistics', 'VendorZ', 30000), ('IT', 'VendorX', 20000)])
print(result)
```

You should see something like:

```text
{'IT': {'total': 75000, 'suppliers': {'VendorX': 60000, 'VendorY': 15000}}, 'Logistics': {'total': 30000, 'suppliers': {'VendorZ': 30000}}}
```

IT spends 75,000 with VendorX taking 60,000 of it - that concentration is your biggest lever in the next negotiation.

## Check yourself

1. What is 'spend concentration' and why care?
2. Name two savings opportunities spend analysis reveals.
3. You see 500 tiny suppliers in office supplies. Action?

<details>
<summary>Show answers</summary>

1. The share of a category going to one supplier - high share means leverage for you, but risk if they fail.

2. Consolidating fragmented suppliers, and spotlighting maverick/off-contract spend.

3. Consolidate to 1-3 with better terms - transaction costs alone justify it.

</details>

## Try this now

Analyze 10 transactions across 3 categories; find the category with the most fragmentation and propose a target supplier count.

---
[← Purchase Price Variance](purchase_price_variance.md) · [Back to Supplier & Procurement library](README.md) · [Maverick Spend Detection →](maverick_spend_detection.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
