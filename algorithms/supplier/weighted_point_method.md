---
title: "Weighted Point Method | supplycm Algorithm Library"
description: "Plain-English explanation of weighted_point_method from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, weighted_point_method, supply chain, plain english, supplier & procurement"
---

# Weighted Point Method

> **Call it:** `from supplycm.supplier import weighted_point_method` · **Level:** Beginner · **You need:** basic arithmetic only

The simplest honest way to pick a supplier: score each one on each criterion, multiply by how much each criterion matters, and add up. The weights force the team to agree on what 'good' means before the winner is known. One list comes back - overall scores per supplier.

**Think of it like this:** Choosing a flat to rent: price 40%, commute 30%, size 30% - and no falling in love with a nice kitchen that scores badly everywhere else.

## When to reach for it

- Any structured supplier or carrier choice with 2-5 criteria
- Defusing arguments by agreeing on weights first, scores second

## Try it with supplycm

```python
from supplycm.supplier import weighted_point_method

result = weighted_point_method(scores=[[8, 7, 9], [6, 9, 7], [7, 8, 6]], weights=[0.5, 0.3, 0.2])
print(result)
```

You should see something like:

```text
[7.9, 7.1, 7.1]
```

Scores per supplier come back - here supplier 1 wins on the weight that matters most (price at 50%).

## Check yourself

1. Why set weights before seeing the scores?
2. Scores are 1-10. Can they be any scale?
3. Two suppliers tie. What now?

<details>
<summary>Show answers</summary>

1. To stop tuning weights to crown the supplier you already liked - weights are strategy, not tactics.

2. Yes - points, 0-100, whatever; just keep every criterion on a comparable scale and state it.

3. Revisit weights (maybe they reveal a real tie), or break the tie on the criterion with the biggest risk.

</details>

## Try this now

Pick a carrier with criteria price/on-time/damage; set weights, score 3 candidates, and defend the winner in two sentences.

---
[Back to Supplier & Procurement library](README.md) · [Supplier Evaluation Matrix →](supplier_evaluation_matrix.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
