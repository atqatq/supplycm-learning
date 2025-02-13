---
title: "Coefficient of Variation | supplycm Algorithm Library"
description: "Plain-English explanation of coefficient_of_variation from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, coefficient_of_variation, supply chain, plain english, statistics & accuracy"
---

# Coefficient of Variation

> **Call it:** `from supplycm.statistics import coefficient_of_variation` · **Level:** Beginner · **You need:** basic arithmetic only

The CV is the standard deviation divided by the mean, shown as a percentage. It measures how noisy demand is relative to its size, so you can compare a slow seller with a fast mover. Low CV (say under 0.2) means steady demand; high CV (above 0.5) means unpredictable demand.

**Think of it like this:** Two drivers both swerve 2 meters - but one is on a highway and one in a parking lot. CV tells you who is really driving wildly relative to their speed.

## When to reach for it

- Classifying products as steady vs erratic before choosing inventory policies
- Comparing demand stability across very different-sized products

## Try it with supplycm

```python
from supplycm.statistics import coefficient_of_variation

result = coefficient_of_variation([100, 105, 98, 102, 99])
print(result)
```

You should see something like:

```text
0.0275
```

The CV is a small number - these sales hug the average, so you can plan this product with confidence.

## Check yourself

1. Product A: mean 100, std 10. Product B: mean 50, std 10. Which has the higher CV?
2. Why not just compare standard deviations directly?
3. What CV would you expect for a fast-selling staple like milk?

<details>
<summary>Show answers</summary>

1. B. Same spread but smaller average, so the noise matters more relative to size (20% vs 10%).

2. Std ignores scale: a std of 10 is tiny for sales of 1,000 but huge for sales of 20. CV puts both on a fair footing.

3. Low, maybe under 0.2 - people buy milk steadily, whatever else happens.

</details>

## Try this now

Compute the CV for two products you know (one steady, one seasonal) and compare them in one sentence.

---
[← Z-Score](zscore.md) · [Back to Statistics & Accuracy library](README.md) · [Min-Max Scaling →](minmax_scale.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
