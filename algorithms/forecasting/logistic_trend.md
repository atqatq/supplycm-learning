---
title: "Logistic Curve | supplycm Algorithm Library"
description: "Plain-English explanation of logistic_trend from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, logistic_trend, supply chain, plain english, forecasting"
---

# Logistic Curve

> **Call it:** `from supplycm.forecasting import logistic_trend` · **Level:** Advanced · **You need:** basic arithmetic only

The Gompertz's symmetrical sibling: an S-curve that rises slowly, speeds through the middle, and decelerates symmetrically toward its ceiling. Logistic curves model diffusion - from smartphones to supermarket products - with an eventual, inevitable plateau.

**Think of it like this:** A rumor spreading through an office: few hear it first, then nearly everyone, and the last holdouts take forever - a symmetric S.

## When to reach for it

- Product diffusion with expected symmetric saturation
- Penetration forecasting for categories with a natural ceiling

## Try it with supplycm

```python
from supplycm.forecasting import logistic_trend

result = logistic_trend([5, 8, 14, 22, 30, 36, 40, 43], horizon=2)
print(result)
```

You should see something like:

```text
[45.15, 9.0381, 0.7229, [43.9275, 44.5483]]
```

Parameters and forecasts approach the curve's ceiling - compare with Gompertz on the same data to see which saturation story fits.

## Check yourself

1. Logistic vs Gompertz - what differs?
2. What business insight hides in the midpoint?
3. Why do forecasters love S-curves?

<details>
<summary>Show answers</summary>

1. Symmetry: logistic decelerates symmetrically; Gompertz is skewed. Fit both and let the data pick.

2. The midpoint is peak growth speed - after it, every plan should assume slower gains.

3. Because adoption really does stop - curves that honor ceilings produce forecasts that age gracefully.

</details>

## Try this now

Fit both S-curves to the same data; compare their 5-period-ahead numbers and their implied ceilings.

---
[← Gompertz Curve](gompertz_trend.md) · [Back to Forecasting library](README.md) · [Brown's Double Exponential Smoothing →](browns_double_exponential.md)
