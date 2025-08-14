---
title: "BOM Explosion | supplycm Algorithm Library"
description: "Plain-English explanation of bom_explosion from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, bom_explosion, supply chain, plain english, mrp & production planning"
---

# BOM Explosion

> **Call it:** `from supplycm.mrp import bom_explosion` · **Level:** Beginner · **You need:** basic arithmetic only

A bill of materials says what a product is made of. Explosion multiplies: if 1 bike needs 2 wheels and 1 frame, then 100 bikes need 200 wheels and 100 frames - and the frame's own parts (paint, bolts) explode too. One call turns product demand into component demand at every level.

**Think of it like this:** A recipe scaled for 50 guests - and every sub-recipe (the sauce inside the dish) scales too.

## When to reach for it

- Turning sales orders into purchasing quantities
- Checking what a big order would actually consume

## Try it with supplycm

```python
from supplycm.mrp import bom_explosion

result = bom_explosion(demand=100, bom={0: [(1, 2.0), (2, 1.0)], 2: [(3, 4.0)]}, parent=0)
print(result)
```

You should see something like:

```text
{1: 200.0, 2: 100.0, 3: 400.0}
```

Component totals come back per item: item 1 gets 200, item 2 gets 100 - and item 3 shows 400 because it lives INSIDE item 2's recipe.

## Check yourself

1. Why does item 3 need 400 units, not 100?
2. What happens with scrap in real factories?
3. Demand for 50 bikes, wheels also sold as spares. How to handle?

<details>
<summary>Show answers</summary>

1. Because 100 parents need 100 of item 2, and each item 2 needs 4 of item 3 - explosion multiplies down the tree.

2. You inflate quantities by a scrap factor first - the plain explosion assumes perfect yields.

3. Add spare demand as independent demand on the wheel - explosion covers only the dependent part.

</details>

## Try this now

Define a 3-level BOM (product -> module -> parts) and explode demand of 60 by hand, then verify with the function.

---
[Back to MRP & Production Planning library](README.md) · [Low-Level Coding →](low_level_coding.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
