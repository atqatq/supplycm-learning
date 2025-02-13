---
title: "Min-Max Scaling | supplycm Algorithm Library"
description: "Plain-English explanation of minmax_scale from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, minmax_scale, supply chain, plain english, statistics & accuracy"
---

# Min-Max Scaling

> **Call it:** `from supplycm.statistics import minmax_scale` · **Level:** Beginner · **You need:** basic arithmetic only

Min-max scaling squeezes all your numbers into a fixed range, usually 0 to 1. The smallest value becomes 0, the biggest becomes 1, and everything else lands in between. Use it when you need to compare or feed values that live on wildly different scales.

**Think of it like this:** Like converting everyone's exam scores from different tests onto one 0-100 curve so they can be ranked fairly.

## When to reach for it

- Preparing supplier scores that use different units (price, days, defects) for one combined ranking
- Making charts where two series of very different sizes fit on one axis

## Try it with supplycm

```python
from supplycm.statistics import minmax_scale

result = minmax_scale([20, 40, 60, 80, 100])
print(result)
```

You should see something like:

```text
[0.0, 0.25, 0.5, 0.75, 1.0]
```

Each value lands between 0 and 1 in the same order as before - the shape of your data never changes, only the ruler.

## Check yourself

1. What do the min and max values always become?
2. Does scaling change the order or spacing pattern of the data?
3. Two suppliers: price 0.9 (scaled), defect rate 0.1 (scaled). Who is better?

<details>
<summary>Show answers</summary>

1. 0 and 1 (the ends of the target range).

2. No - it only stretches or squeezes the ruler, the pattern stays identical.

3. It depends on direction: for price, low is good; for defects, low is good. Always note which way each score points before combining them.

</details>

## Try this now

Scale these lead times to 0-1: [2, 5, 5, 9, 12] days, and say which day is the 'most typical' in scaled form.

---
[← Coefficient of Variation](coefficient_of_variation.md) · [Back to Statistics & Accuracy library](README.md) · [Outlier Detection (IQR) →](outlier_detection_iqr.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
