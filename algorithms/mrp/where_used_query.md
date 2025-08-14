---
title: "Where-Used Query | supplycm Algorithm Library"
description: "Plain-English explanation of where_used_query from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, where_used_query, supply chain, plain english, mrp & production planning"
---

# Where-Used Query

> **Call it:** `from supplycm.mrp import where_used_query` · **Level:** Beginner · **You need:** basic arithmetic only

The reverse of explosion: given a component, find every parent that uses it. If a bolt is being discontinued or a price jumps, where-used tells you the blast radius in one call. Every engineer and buyer lives by this query.

**Think of it like this:** Searching which of your recipes use butter before learning the price tripled.

## When to reach for it

- Impact analysis before a part change or discontinuation
- Costing exercises: which products does this component price hit?

## Try it with supplycm

```python
from supplycm.mrp import where_used_query

result = where_used_query(bom={0: [1, 2], 1: [3], 2: [3, 4], 5: [3]}, component=3)
print(result)
```

You should see something like:

```text
[0, 1, 2, 5]
```

Parents [1, 2, 5] come back - item 3 feeds three different parents, so any change to it touches three products.

## Check yourself

1. Component used by 5 parents, one is being discontinued. What now?
2. Where-used vs pegging - difference?
3. Why is this query critical for substitutions?

<details>
<summary>Show answers</summary>

1. 4 parents still depend on it - demand drops but does not vanish; update forecasts accordingly.

2. Where-used lists ALL possible parents statically; pegging traces a specific requirement to ITS source order.

3. You must know every affected product BEFORE switching a part - surprises here are recalls.

</details>

## Try this now

Build a small 4-product BOM, pick the most shared component, and list every product its price increase would hit.

---
[← Low-Level Coding](low_level_coding.md) · [Back to MRP & Production Planning library](README.md) · [Modular BOM →](modular_bom.md)
