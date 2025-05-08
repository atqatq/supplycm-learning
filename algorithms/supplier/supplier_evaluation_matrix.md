---
title: "Supplier Evaluation Matrix | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_evaluation_matrix from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_evaluation_matrix, supply chain, plain english, supplier & procurement"
---

# Supplier Evaluation Matrix

> **Call it:** `from supplycm.supplier import supplier_evaluation_matrix` · **Level:** Beginner · **You need:** basic arithmetic only

Turns a table of raw scores into a clean nested structure: supplier -> criterion -> score. It is the plumbing behind scorecards and weighted rankings - one tidy object you can pass around, print, or feed into the weighted methods.

**Think of it like this:** Filling in the grid before scoring the game: names down the side, categories across the top, no cell left blank.

## When to reach for it

- Organizing an RFP scoring session's raw output
- Preparing data for weighted_point_method or vendor_scorecard

## Try it with supplycm

```python
from supplycm.supplier import supplier_evaluation_matrix

result = supplier_evaluation_matrix(['Alpha', 'Beta'], ['price', 'quality', 'lead_time'], [[80, 90, 70], [75, 85, 90]])
print(result)
```

You should see something like:

```text
{'Alpha': {'price': 80, 'quality': 90, 'lead_time': 70}, 'Beta': {'price': 75, 'quality': 85, 'lead_time': 90}}
```

Alpha reads 80/90/70, Beta 75/85/90 - now the conversation is about specific cells, not vague impressions.

## Check yourself

1. What shape is the output?
2. Before weighting, what should you check in the raw matrix?
3. A supplier has a missing score. What do you do?

<details>
<summary>Show answers</summary>

1. A dict of dicts: suppliers as keys, each holding criterion -> score.

2. That all criteria point the same way (higher = better) - flip cost-type scores if needed.

3. Score it before comparison - gaps quietly bias totals and hide real differences.

</details>

## Try this now

Build a 4-supplier matrix for price/quality/delivery/risk and mark each cell good/mid/bad before any weighting.

---
[← Weighted Point Method](weighted_point_method.md) · [Back to Supplier & Procurement library](README.md) · [Vendor Scorecard →](vendor_scorecard.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
