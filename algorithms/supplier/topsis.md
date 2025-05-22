---
title: "TOPSIS | supplycm Algorithm Library"
description: "Plain-English explanation of topsis from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, topsis, supply chain, plain english, supplier & procurement"
---

# TOPSIS

> **Call it:** `from supplycm.supplier import topsis` · **Level:** Advanced · **You need:** basic arithmetic only

TOPSIS ranks alternatives by geometric intuition: the best option is simultaneously closest to an ideal one and farthest from the worst imaginable one. Feed a decision matrix, weights, and which criteria are benefits vs costs - out comes a ranking, best first.

**Think of it like this:** Choosing a flat by distance to your dream flat and distance from your nightmare - the winner minimizes both gaps.

## When to reach for it

- Ranking several suppliers on mixed benefit/cost criteria
- Adding a transparent, repeatable method to committee decisions

## Try it with supplycm

```python
from supplycm.supplier import topsis

result = topsis(decision_matrix=[[8, 120], [7, 100], [9, 150]], weights=[0.6, 0.4], criteria_type=['benefit', 'cost'])
print(result)
```

You should see something like:

```text
[0, 1, 2]
```

A ranking of indices, best first - here the second supplier wins by balancing quality and the lower price.

## Check yourself

1. What do 'benefit' and 'cost' criteria mean here?
2. Why must criteria be normalized first?
3. TOPSIS picks A, your gut says B. Next move?

<details>
<summary>Show answers</summary>

1. Benefit: more is better (quality). Cost: less is better (price) - TOPSIS flips cost columns before comparing.

2. Raw units differ (points vs dollars); normalization puts everything on one fair scale before weighting.

3. Inspect the inputs - usually a weight or a criterion direction disagrees with reality; the method only reflects what you fed it.

</details>

## Try this now

Add a fourth supplier with great price, poor quality; show how the ranking shifts as the quality weight rises from 0.4 to 0.7.

---
[← ANP (Analytic Network Process)](analytic_network_process.md) · [Back to Supplier & Procurement library](README.md) · [Fuzzy TOPSIS →](fuzzy_topsis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
