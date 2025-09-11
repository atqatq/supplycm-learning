---
title: "ABC-XYZ Matrix | supplycm Algorithm Library"
description: "Plain-English explanation of abc_xyz_matrix from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, abc_xyz_matrix, supply chain, plain english, inventory"
---

# ABC-XYZ Matrix

> **Call it:** `from supplycm.inventory import abc_xyz_matrix` · **Level:** Intermediate · **You need:** basic arithmetic only

The 3x3 grid where value meets predictability: every item lands in a cell like AX (big and steady - automate and shine) or CZ (small and chaotic - keep it cheap and simple). This function assigns the combined class, turning two analyses into one policy map.

**Think of it like this:** Sorting students by grades (ABC) AND attendance consistency (XYZ) - each of the nine boxes gets a different coaching plan.

## When to reach for it

- Designing per-class inventory and forecasting policies
- Deciding where planners spend time vs where rules run alone

## Try it with supplycm

```python
from supplycm.inventory import abc_xyz_matrix

result = abc_xyz_matrix(abc_classes=[('milk', 'A'), ('umbrella', 'C')], xyz_classes=[('milk', 'X'), ('umbrella', 'Z')])
print(result)
```

You should see something like:

```text
[['milk', 'A', 'X', 'AX'], ['umbrella', 'C', 'Z', 'CZ']]
```

Milk is AX, umbrellas CZ - milk gets tight automated control; umbrellas get the cheapest sensible policy and no analyst hours.

## Check yourself

1. Name the four most talked-about cells and their strategies.
2. Which cell hurts most when managed carelessly?
3. What does this matrix replace?

<details>
<summary>Show answers</summary>

1. AX: automate tightly; AZ: watch closely, smart methods; CX: simple rules; CZ: minimal effort, minimal stock.

2. AZ - high value with chaos; mistakes are expensive and frequent-feeling.

3. One-size-fits-all policies - the grid is permission to treat different items differently.

</details>

## Try this now

Place 8 real-ish products in the grid and write a one-line policy for each occupied cell.

---
[← XYZ Analysis](xyz_analysis.md) · [Back to Inventory library](README.md) · [Inventory Position →](inventory_position.md)
