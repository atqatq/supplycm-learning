---
title: "Box-Cox Transform | supplycm Algorithm Library"
description: "Plain-English explanation of box_cox_transform from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, box_cox_transform, supply chain, plain english, forecasting"
---

# Box-Cox Transform

> **Call it:** `from supplycm.forecasting import box_cox_transform` · **Level:** Advanced · **You need:** basic arithmetic only

Some series wobble MORE as they grow - multiplicative noise. Box-Cox reshapes the values (log-like) so variation becomes steadier and patterns simpler for models to learn. The lambda parameter tunes the reshaping; models run on the transformed scale, then results come back via the inverse.

**Think of it like this:** Taking a photo of a sunset in RAW format: the transform doesn't change the scene - it arranges the same information so the tools can work with it.

## When to reach for it

- Growing series where percentage swings stay constant
- Preparing data for models that prefer stable variance

## Try it with supplycm

```python
from supplycm.forecasting import box_cox_transform

result = box_cox_transform([100, 110, 121, 133, 146], lam=0.0)
print(result)
```

You should see something like:

```text
[4.6052, 4.7005, 4.7958, 4.8903, 4.9836]
```

Transformed values with steadier spacing - the compounding series now looks closer to a tidy straight line on the working scale.

## Check yourself

1. What does lambda = 0 mean?
2. Why transform at all if we inverse later?
3. How do you get real units back?

<details>
<summary>Show answers</summary>

1. The log transform - the classic choice for multiplicative, percentage-growing series.

2. Because models learn better on steady-variance data - the transform is scaffolding, removed once the structure is built.

3. The inverse Box-Cox - always forecast on the transformed scale, then convert results home.

</details>

## Try this now

Transform a compounding series with lambda 0 and 1; plot both mentally and pick the one with steadier spread.

---
[← Theil's U](theils_u.md) · [Back to Forecasting library](README.md) · [Inverse Box-Cox Transform →](inverse_box_cox.md)
