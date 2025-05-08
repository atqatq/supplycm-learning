---
title: "Supplier Diversity Index | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_diversity_index from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_diversity_index, supply chain, plain english, supplier & procurement"
---

# Supplier Diversity Index

> **Call it:** `from supplycm.supplier import supplier_diversity_index` · **Level:** Intermediate · **You need:** basic arithmetic only

Scores how evenly spend is spread across suppliers on a 0-1 scale: 1 means perfectly spread, near 0 means almost everything goes to one supplier. It is a one-number risk gauge for concentration - the mirror image of consolidation leverage.

**Think of it like this:** An investment portfolio: all eggs in one basket scores 0; a balanced basket scores high.

## When to reach for it

- Risk reviews: how exposed are we to our biggest supplier?
- Tracking supplier-base health after consolidation programs

## Try it with supplycm

```python
from supplycm.supplier import supplier_diversity_index

result = supplier_diversity_index(spend_per_supplier=[60000, 20000, 10000, 10000])
print(result)
```

You should see something like:

```text
0.58
```

A middling score - heavy tilt toward the first supplier; every concentration report should show this number next to the top supplier's share.

## Check yourself

1. Index drops from 0.8 to 0.3 in a year. What happened?
2. Is a high diversity index always good?
3. Two categories, same index. Same risk?

<details>
<summary>Show answers</summary>

1. Spend concentrated - a consolidation program, a single-sourcing decision, or a competitor exit. Verify it was deliberate.

2. No - over-fragmentation loses leverage. The index flags concentration risk; strategy decides the sweet spot.

3. Not necessarily - risk also depends on switch costs and market depth, which the index cannot see.

</details>

## Try this now

Compute the index for spend [90000, 5000, 3000, 2000]; then for an even 4-way split, and write the risk takeaway.

---
[← Supplier Consolidation](supplier_consolidation.md) · [Back to Supplier & Procurement library](README.md) · [Negotiation Zone (ZOPA) →](negotiation_zone.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
