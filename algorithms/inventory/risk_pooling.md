---
title: "Risk Pooling Effect | supplycm Algorithm Library"
description: "Plain-English explanation of risk_pooling from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, risk_pooling, supply chain, plain english, inventory"
---

# Risk Pooling Effect

> **Call it:** `from supplycm.inventory import risk_pooling` · **Level:** Intermediate · **You need:** basic arithmetic only

Pooling demand across locations (or products) shrinks relative variability: the pooled standard deviation is smaller than the sum of individual ones, so central stocks cover more with less. This quantifies the safety stock benefit of combining demand streams.

**Think of it like this:** A shared emergency fund among friends covers bad months with less total cash than everyone hoarding separately.

## When to reach for it

- Evaluating centralization vs regional stocking
- Deciding whether two product variants can share one generic stock

## Try it with supplycm

```python
from supplycm.inventory import risk_pooling

result = risk_pooling(demands=[120, 80, 100], lead_times=[4, 4, 4])
print(result)
```

You should see something like:

```text
0.5793
```

The pooled requirement versus the sum of separate ones - the difference is the safety stock money pooling saves.

## Check yourself

1. When does pooling help most?
2. What weakens pooling?
3. Name a real pooling play.

<details>
<summary>Show answers</summary>

1. When demands are independent and roughly equal in size - variety cancels out and the pool rides smoother.

2. Correlated demand (all regions peak together) and wildly unequal scales - one giant demand dominates the pool.

3. Generic components stocked for multiple finished variants, or one national DC replacing regional stockrooms.

</details>

## Try this now

Pool three invented regional demands with a lead time of 2; report the savings vs holding separately.

---
[← Square Root Law of Inventory](square_root_law.md) · [Back to Inventory library](README.md) · [Bullwhip Effect Ratio →](bullwhip_effect.md)
