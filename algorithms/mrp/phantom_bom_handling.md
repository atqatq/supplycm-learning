---
title: "Phantom BOM Handling | supplycm Algorithm Library"
description: "Plain-English explanation of phantom_bom_handling from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, phantom_bom_handling, supply chain, plain english, mrp & production planning"
---

# Phantom BOM Handling

> **Call it:** `from supplycm.mrp import phantom_bom_handling` · **Level:** Advanced · **You need:** basic arithmetic only

A phantom is a logical grouping in the BOM that is never built or stocked as a real item - an assembly that exists on paper only. Explosion passes THROUGH phantoms to their components. This computes requirements while skipping phantoms entirely.

**Think of it like this:** A 'salad' line on the recipe card that is really just lettuce + tomato + dressing - you shop for ingredients, never for 'a salad'.

## When to reach for it

- Engineering subassemblies used only during assembly, never stored
- Keeping MRP focused on real buy/make items

## Try it with supplycm

```python
from supplycm.mrp import phantom_bom_handling

result = phantom_bom_handling(bom={0: [(1, 1.0), (2, 2.0)], 1: [(3, 4.0)]}, phantoms={1}, top_item=0, demand=50)
print(result)
```

You should see something like:

```text
{1: 50.0, 2: 100.0}
```

Item 3's requirement flows straight to 200 (via phantom item 1), while item 2 shows 100 - the phantom itself never appears in any plan.

## Check yourself

1. Why do phantoms exist at all?
2. What would happen if a phantom were treated as real?
3. When is an assembly NOT a phantom?

<details>
<summary>Show answers</summary>

1. To organize drawings and engineering structure without forcing planning of items nobody stocks.

2. MRP would demand you build and stock an assembly that is consumed instantly - pure noise.

3. When it is actually built, tested, and stored as a sellable or service part.

</details>

## Try this now

Mark item 1 as real instead of phantom and contrast the two requirement outputs.

---
[← Pegging](pegging.md) · [Back to MRP & Production Planning library](README.md) · [Cycle Counting Plan →](cycle_counting.md)
