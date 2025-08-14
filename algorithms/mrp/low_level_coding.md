---
title: "Low-Level Coding | supplycm Algorithm Library"
description: "Plain-English explanation of low_level_coding from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, low_level_coding, supply chain, plain english, mrp & production planning"
---

# Low-Level Coding

> **Call it:** `from supplycm.mrp import low_level_coding` · **Level:** Intermediate · **You need:** basic arithmetic only

Low-level coding stamps every part with the LOWEST level where it appears anywhere in the BOM tree. Why care? MRP must plan a shared part only AFTER all its parents are planned - level codes guarantee that order. It is the plumbing rule that keeps explosion correct.

**Think of it like this:** A building's floors: you schedule the roof only after the floor below it is scheduled - even if the roof also appears over the garage.

## When to reach for it

- Before running MRP on a BOM where parts appear at multiple levels
- Sanity-checking messy inherited BOMs

## Try it with supplycm

```python
from supplycm.mrp import low_level_coding

result = low_level_coding(bom={0: [1, 2], 1: [3], 2: [3]})
print(result)
```

You should see something like:

```text
{3: 0, 1: 1, 2: 1, 0: 2}
```

Item 3 gets level 2 - even though it first appears at level 2 via item 1... it appears there AND under item 2, so it is coded by the deepest path.

## Check yourself

1. What breaks if you skip low-level coding?
2. Item X appears at level 1 in one product and level 3 in another. Its code?
3. Who computes level codes in real systems?

<details>
<summary>Show answers</summary>

1. MRP might plan the shared part too early, from one parent only, and miss the other parent's requirement.

2. 3 - the LOWEST (deepest) level anywhere in any bill.

3. The MRP system itself, after every BOM change - but you should understand what it is doing.

</details>

## Try this now

Add item 3 as a direct child of 0 in the example and recompute - watch its low-level code stay driven by the deepest path.

---
[← BOM Explosion](bom_explosion.md) · [Back to MRP & Production Planning library](README.md) · [Where-Used Query →](where_used_query.md)
