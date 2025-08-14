---
title: "Backflush | supplycm Algorithm Library"
description: "Plain-English explanation of backflush from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, backflush, supply chain, plain english, mrp & production planning"
---

# Backflush

> **Call it:** `from supplycm.mrp import backflush` · **Level:** Intermediate · **You need:** basic arithmetic only

Instead of recording every part issued to the floor, backflush DEDUCTS the whole recipe when the finished unit is reported done: 100 bikes done means 200 wheels and 100 frames leave inventory automatically. It is the standard shop-floor shortcut - with real data-quality risks.

**Think of it like this:** Billing a set menu: you do not charge bread, main, and dessert separately - one order price, ingredients assumed.

## When to reach for it

- Repetitive production where tracking each bolt is impossible
- Clean processes with reliable yields and accurate BOMs

## Try it with supplycm

```python
from supplycm.mrp import backflush

result = backflush(completed_qty=100, bom={0: [(1, 2.0), (2, 1.0), (3, 4.0)]}, item=0)
print(result)
```

You should see something like:

```text
{1: 200.0, 2: 100.0, 3: 400.0}
```

Component deductions come back as a dict - 200 of item 1, 100 of item 2, 400 of item 3 vanish from stock per the recipe.

## Check yourself

1. What is backflush's big risk?
2. When should you NOT backflush?
3. How do healthy backflush users keep stock honest?

<details>
<summary>Show answers</summary>

1. Silent drift: scrap, substitutions, and BOM errors accumulate as phantom inventory discrepancies.

2. High-scrap processes, expensive tracked components, or where batch records are legally required.

3. Cycle counting plus exception alerts for unusually large deductions.

</details>

## Try this now

Backflush 50 finished units through a 4-component BOM; identify which component you would still track manually and why.

---
[← Lead Time Offsetting](lead_time_offsetting.md) · [Back to MRP & Production Planning library](README.md) · [MRP Calculation →](mrp_calculation.md)
