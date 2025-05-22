---
title: "Supplier Segmentation (Kraljic) | supplycm Algorithm Library"
description: "Plain-English explanation of supplier_segmentation from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, supplier_segmentation, supply chain, plain english, supplier & procurement"
---

# Supplier Segmentation (Kraljic)

> **Call it:** `from supplycm.supplier import supplier_segmentation` · **Level:** Beginner · **You need:** basic arithmetic only

The Kraljic matrix places every supplier on two axes - profit impact and supply risk - into four boxes: Strategic (high/high), Leverage (high/low), Bottleneck (low/high), Routine (low/low). Each box has its own playbook; treating a routine supplier like a strategic one wastes effort, and vice versa.

**Think of it like this:** Sorting your contacts: family (strategic), your best-terms regulars (leverage), the rare specialist (bottleneck), and acquaintances (routine).

## When to reach for it

- Building the annual sourcing strategy per category
- Deciding where relationship-building vs hard negotiation pays off

## Try it with supplycm

```python
from supplycm.supplier import supplier_segmentation

result = supplier_segmentation(suppliers=[('SteelCo', 0.9, 0.8), ('BoxCo', 0.7, 0.2), ('SealCo', 0.2, 0.9), ('PenCo', 0.1, 0.1)])
print(result)
```

You should see something like:

```text
[['SteelCo', 'Strategic'], ['BoxCo', 'Leverage'], ['SealCo', 'Bottleneck'], ['PenCo', 'Routine']]
```

SteelCo is Strategic, BoxCo Leverage, SealCo Bottleneck, PenCo Routine - four suppliers, four completely different management styles.

## Check yourself

1. Name the four Kraljic quadrants and one tactic each.
2. Where does the office stationery supplier sit?
3. A bottleneck supplier just raised prices 30%. Options?

<details>
<summary>Show answers</summary>

1. Strategic: partnership; Leverage: compete the business; Bottleneck: secure supply/stock up; Routine: automate and simplify.

2. Routine - low impact, low risk; the goal is minimal effort via catalogs and p-cards.

3. Qualify alternatives, redesign the spec, hold buffer stock - the quadrant's whole point is to never be surprised here.

</details>

## Try this now

Place 6 real suppliers in the matrix; write one-line playbooks for each quadrant you filled.

---
[← Preferred Supplier Index](preferred_supplier_index.md) · [Back to Supplier & Procurement library](README.md) · [Total Cost of Ownership (TCO) →](total_cost_of_ownership.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
