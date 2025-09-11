---
title: "XYZ Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of xyz_analysis from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, xyz_analysis, supply chain, plain english, inventory"
---

# XYZ Analysis

> **Call it:** `from supplycm.inventory import xyz_analysis` · **Level:** Intermediate · **You need:** basic arithmetic only

XYZ measures predictability instead of value: X items sell steadily (low variation), Y items swing with season or trend, Z items are chaotic. It needs only demand history. Pair it with ABC and you know both what MATTERS and what's PREDICTABLE.

**Think of it like this:** Classifying friends by reliability: some show up like clockwork (X), some run hot and cold (Y), and some are pure chaos (Z).

## When to reach for it

- Choosing forecasting methods per item (X: simple; Z: judgment)
- Setting inventory strategies: X needs small buffers, Z needs big ones or none

## Try it with supplycm

```python
from supplycm.inventory import xyz_analysis

result = xyz_analysis(demand_series=[('steady', [100, 102, 99, 101, 100, 103]), ('spiky', [5, 90, 2, 130, 1, 80])])
print(result)
```

You should see something like:

```text
[['steady', 'X', 0.0146], ['spiky', 'Z', 1.0888]]
```

'steady' lands as X, 'spiky' as Z - the classes decide forecast method and buffer style per item.

## Check yourself

1. What does XYZ measure that ABC ignores?
2. An AZ item - what's the policy dilemma?
3. Which class suits full automation?

<details>
<summary>Show answers</summary>

1. Variability/predictability of demand - ABC's value lens says nothing about how forecastable an item is.

2. High value, chaotic demand: expensive to buffer, painful to miss - needs smart methods and judgment, not rules of thumb.

3. X items - steady demand makes simple, automatic policies reliable.

</details>

## Try this now

XYZ-classify 6 items from invented histories; note which two you would never let a simple rule run alone.

---
[← ABC Analysis](abc_analysis.md) · [Back to Inventory library](README.md) · [ABC-XYZ Matrix →](abc_xyz_matrix.md)
