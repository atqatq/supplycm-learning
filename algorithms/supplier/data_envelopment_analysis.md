---
title: "Data Envelopment Analysis (DEA) | supplycm Algorithm Library"
description: "Plain-English explanation of data_envelopment_analysis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, data_envelopment_analysis, supply chain, plain english, supplier & procurement"
---

# Data Envelopment Analysis (DEA)

> **Call it:** `from supplycm.supplier import data_envelopment_analysis` · **Level:** Advanced · **You need:** basic arithmetic only

DEA benchmarks efficiency relatively: each supplier or plant is scored 0-1 by comparing its outputs (deliveries, quality) to its inputs (cost, labor) against a frontier built by the best performers. A score of 1.0 means 'on the frontier'; 0.8 means this unit could theoretically deliver the same with 20% fewer inputs.

**Think of it like this:** Students graded against the best realistic performance in THEIR class - everyone can see how far ahead the leaders are and who sets the pace.

## When to reach for it

- Benchmarking suppliers or plants with different sizes and mixes
- Finding which inefficient units have the most to learn, and from whom

## Try it with supplycm

```python
from supplycm.supplier import data_envelopment_analysis

result = data_envelopment_analysis(inputs=[[10, 5], [20, 8], [15, 6]], outputs=[[100, 90], [150, 140], [140, 100]])
print(result)
```

You should see something like:

```text
[1.0, 0.8177, 0.9023]
```

Efficiency scores in 0-1: the unit scoring lowest converts inputs to outputs worst - and the frontier units show what 'better' looks like in practice.

## Check yourself

1. What does an efficiency score of 0.75 mean?
2. Why is DEA fair for comparing different-sized units?
3. A small unit scores 1.0 and a giant 0.7. Is the small one 'better'?

<details>
<summary>Show answers</summary>

1. This unit could produce its current outputs with about 75% of the inputs the best performers would need.

2. It compares ratios and builds each unit's own reference frontier - scale matters less than conversion efficiency.

3. At converting inputs to outputs, yes - but check absolute capacity and strategic fit before crowning anyone.

</details>

## Try this now

DEA 4 warehouses on inputs (cost, staff) and outputs (orders, on-time %); identify the laggard and its frontier twin to copy.

---
[← ELECTRE](electre.md) · [Back to Supplier & Procurement library](README.md) · [Strategic Supplier Scorecard →](strategic_supplier_scorecard.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
