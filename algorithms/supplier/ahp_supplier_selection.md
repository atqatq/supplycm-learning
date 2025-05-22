---
title: "AHP Supplier Selection | supplycm Algorithm Library"
description: "Plain-English explanation of ahp_supplier_selection from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, ahp_supplier_selection, supply chain, plain english, supplier & procurement"
---

# AHP Supplier Selection

> **Call it:** `from supplycm.supplier import ahp_supplier_selection` · **Level:** Advanced · **You need:** basic arithmetic only

AHP takes your pairwise comparisons - 'quality is 3x more important than price' - and turns them into clean criterion weights that always sum to 1. It forces consistent thinking: if A beats B and B beats C, A should beat C. The output feeds directly into scoring suppliers.

**Think of it like this:** Rock-paper-scissors discipline for criteria: every pair meets once, and consistency is enforced across the whole tournament.

## When to reach for it

- Structured weight-setting workshops with several stakeholders
- Any multi-criteria decision where weights must be defensible

## Try it with supplycm

```python
from supplycm.supplier import ahp_supplier_selection

result = ahp_supplier_selection([[1, 3, 5], [1/3, 1, 3], [1/5, 1/3, 1]])
print(result)
```

You should see something like:

```text
[0.6333, 0.2605, 0.1062]
```

Weights near 0.63 / 0.26 / 0.11 - quality dominates because you called it 3x price and 5x delivery; the weights now carry that judgment honestly.

## Check yourself

1. What does a pairwise entry of 3 mean?
2. Why must AHP weights sum to 1?
3. Judgments contradict each other. What does AHP do about it?

<details>
<summary>Show answers</summary>

1. The row criterion is 3 times more important than the column criterion (and the mirror cell is 1/3).

2. So they are shares of importance - comparable and complete, with no hidden extra weight.

3. The averaging exposes inconsistency - big contradictions show up as odd weights and get reconsidered.

</details>

## Try this now

Compare 4 criteria pairwise for a packaging supplier; verify weights sum to 1 and defend the biggest one.

---
[← Should-Cost Analysis](should_cost_analysis.md) · [Back to Supplier & Procurement library](README.md) · [ANP (Analytic Network Process) →](analytic_network_process.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
