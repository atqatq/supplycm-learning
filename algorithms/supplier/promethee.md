---
title: "PROMETHEE | supplycm Algorithm Library"
description: "Plain-English explanation of promethee from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, promethee, supply chain, plain english, supplier & procurement"
---

# PROMETHEE

> **Call it:** `from supplycm.supplier import promethee` · **Level:** Advanced · **You need:** basic arithmetic only

PROMETHEE compares every alternative pair on every criterion, asking 'how MUCH does A beat B here?' via preference thresholds, then sums the evidence into positive and negative flows. High positive flow = often preferred; high negative = often the loser. The two flows give a nuanced ranking.

**Think of it like this:** Round-robin match points: not just who won, but how convincingly each victory was.

## When to reach for it

- Ranking suppliers where margins of victory matter, not just wins
- Decisions with meaningful indifference bands (tiny differences shouldn't count)

## Try it with supplycm

```python
from supplycm.supplier import promethee

result = promethee(decision_matrix=[[3, 5], [4, 4], [2, 6]], weights=[0.5, 0.5], preference_threshold=0.5, indifference_threshold=0.1)
print(result)
```

You should see something like:

```text
[[0.5, 0.5, 0.5], [0.5, 0.5, 0.5]]
```

Two flow lists come back - the supplier with strongly positive net flow is the robust all-round performer here.

## Check yourself

1. What does the indifference threshold do?
2. Positive vs negative flow - what does each measure?
3. Two options have near-equal flows. Decision?

<details>
<summary>Show answers</summary>

1. Differences smaller than it count as a tie - it stops decimals deciding outcomes that are practically equal.

2. Positive: how strongly this option beats others; negative: how strongly it loses. Net flow combines them.

3. Treat as a tie - break with strategy (risk, relationship, capacity), not by inventing precision.

</details>

## Try this now

Rank 4 packaging suppliers with PROMETHEE; identify which pair is effectively tied and say what would separate them.

---
[← Fuzzy TOPSIS](fuzzy_topsis.md) · [Back to Supplier & Procurement library](README.md) · [ELECTRE →](electre.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
