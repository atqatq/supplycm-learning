---
title: "Supplier Consolidation | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_consolidation from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_consolidation, supply chain, plain english, supplier & procurement"
---

# Supplier Consolidation

> **Call it:** `from supplycm.supplier import supplier_consolidation` · **Level:** Intermediate · **You need:** basic arithmetic only

Shows what happens if you move a chosen share of spend to fewer suppliers: the consolidated amount and the remaining spread. Fewer suppliers usually mean better prices and simpler management - balanced against less competition and more dependency.

**Think of it like this:** Moving from 12 small savings accounts to 3: better rates, less admin - but now one bank failure stings more.

## When to reach for it

- Planning a supplier-base rationalization program
- Estimating the spend pool that would move to a strategic partner

## Try it with supplycm

```python
from supplycm.supplier import supplier_consolidation

result = supplier_consolidation(current_spend=[50000, 40000, 30000, 20000, 10000], consolidation_ratio=0.4)
print(result)
```

You should see something like:

```text
[6000.0, 3]
```

A large pool moves to preferred suppliers while a long tail remains - keep enough of that tail alive to preserve competitive pressure.

## Check yourself

1. What do you gain by consolidating suppliers?
2. What do you risk?
3. How many suppliers is 'right' for a category?

<details>
<summary>Show answers</summary>

1. Volume discounts, fewer relationships to manage, deeper collaboration, better service priority.

2. Dependency: a failure, price hike, or quality slip hits harder with fewer alternatives.

3. Enough for competition and security (often 2-3) - decide per category on criticality, not globally.

</details>

## Try this now

Consolidate a 6-supplier base at 50% and name the two risks you would mitigate first.

---
[← Maverick Spend Detection](maverick_spend_detection.md) · [Back to Supplier & Procurement library](README.md) · [Supplier Diversity Index →](supplier_diversity_index.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
