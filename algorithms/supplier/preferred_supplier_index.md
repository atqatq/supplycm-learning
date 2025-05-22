---
title: "Preferred Supplier Index | supplycm Algorithm Library"
description: "Plain-English explanation of preferred_supplier_index from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, preferred_supplier_index, supply chain, plain english, supplier & procurement"
---

# Preferred Supplier Index

> **Call it:** `from supplycm.supplier import preferred_supplier_index` · **Level:** Intermediate · **You need:** basic arithmetic only

Combines weighted supplier scores against a pass threshold: everyone above the line becomes 'preferred' and gets the easy buying path. It is the enforcement engine behind catalog buying - suppliers qualify by number, not by history or favoritism.

**Think of it like this:** A bouncer's guest list: meet the score, you are on the list; fall below, you wait outside (or improve).

## When to reach for it

- Running a preferred-supplier program
- Deciding which suppliers get auto-approved for standard purchases

## Try it with supplycm

```python
from supplycm.supplier import preferred_supplier_index

result = preferred_supplier_index(suppliers=[{'name': 'Alpha', 'quality': 80, 'delivery': 90}, {'name': 'Beta', 'quality': 60, 'delivery': 65}], weights={'quality': 0.5, 'delivery': 0.5}, threshold=70)
print(result)
```

You should see something like:

```text
['Alpha']
```

Only Alpha clears 70 - Beta stays off the preferred list until its scores recover.

## Check yourself

1. What does the threshold actually control?
2. A long-time supplier drops below threshold. Now what?
3. How does this connect to maverick spend?

<details>
<summary>Show answers</summary>

1. How exclusive the preferred list is - too low and it means nothing, too high and buyers route around it.

2. Same rule as everyone: remediation plan with a date, or lose preferred status - consistency builds program trust.

3. It shrinks it: when preferred suppliers are genuinely good and easy to buy from, going around them stops making sense.

</details>

## Try this now

Set a threshold for 4 scored suppliers so exactly two qualify; justify the cut in one sentence.

---
[← Supplier Risk Score](supplier_risk_score.md) · [Back to Supplier & Procurement library](README.md) · [Supplier Segmentation (Kraljic) →](supplier_segmentation.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
