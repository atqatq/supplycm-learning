---
title: "ANP (Analytic Network Process) | supplycm Algorithm Library"
description: "Plain-English explanation of analytic_network_process from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, analytic_network_process, supply chain, plain english, supplier & procurement"
---

# ANP (Analytic Network Process)

> **Call it:** `from supplycm.supplier import analytic_network_process` · **Level:** Advanced · **You need:** basic arithmetic only

ANP is AHP's big sibling for messy reality: criteria can influence EACH OTHER, not just the alternatives. You supply cluster comparisons plus inner-dependence matrices, and ANP resolves the web into final weights. Use it when criteria genuinely interact - like price affecting quality perception.

**Think of it like this:** AHP is a tournament of individuals; ANP is a league where teams affect each other's form before the final ranking.

## When to reach for it

- Complex strategic sourcing decisions with interacting criteria
- Academic-grade evaluations where dependencies cannot be ignored

## Try it with supplycm

```python
from supplycm.supplier import analytic_network_process

result = analytic_network_process(cluster_matrix=[[1, 2], [1/2, 1]], inner_dependence={0: [[1]], 1: [[1, 1/2], [2, 1]]})
print(result)
```

You should see something like:

```text
[0.6667, 0.3333]
```

Weights emerge from the whole influence web - they reflect both direct importance and how criteria reinforce each other.

## Check yourself

1. When does ANP beat plain AHP?
2. What does inner_dependence encode?
3. Cost of ANP over AHP?

<details>
<summary>Show answers</summary>

1. When criteria influence one another - e.g., supplier reputation affects perceived quality - and ignoring it would skew weights.

2. How criteria inside a cluster shape each other, as its own mini comparison matrix.

3. Many more judgments to collect - use it when the decision is big enough to deserve the rigor.

</details>

## Try this now

Identify one real dependency between two sourcing criteria; explain how ignoring it would bias a plain weighted score.

---
[← AHP Supplier Selection](ahp_supplier_selection.md) · [Back to Supplier & Procurement library](README.md) · [TOPSIS →](topsis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
