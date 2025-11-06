---
title: "Croston's Method | supplycm Algorithm Library"
description: "Plain-English explanation of crostons_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, crostons_method, supply chain, plain english, forecasting"
---

# Croston's Method

> **Call it:** `from supplycm.forecasting import crostons_method` · **Level:** Intermediate · **You need:** basic arithmetic only

For intermittent demand - mostly zeros with occasional sales - Croston tracks TWO things separately: how BIG a sale is when it happens, and how LONG between sales. The forecast is the smoothed size divided by the smoothed interval. It refuses to average zeros into nonsense.

**Think of it like this:** A vending machine mechanic: how much stock each repair consumes, and how often repairs happen - plan from the pair, not from daily averages.

## When to reach for it

- Spare parts, slow-moving SKUs, size-phenomenon demand
- Any series dominated by zeros that ordinary smoothing turns to mush

## Try it with supplycm

```python
from supplycm.forecasting import crostons_method

result = crostons_method([2, 0, 0, 5, 0, 3, 0, 0], alpha=0.2)
print(result)
```

You should see something like:

```text
[[2, 2, 2, 2.6, 2.6, 2.68, 2.68, 2.68], [1.0, 1.0, 1.0, 1.4, 1.4, 1.52, 1.52, 1.52]]
```

Two estimates return: smoothed demand size (~2.7) and smoothed interval (~1.5) - their ratio is the per-period forecast; zeros no longer lie.

## Check yourself

1. Why do standard methods fail on intermittent demand?
2. What are the two tracked components?
3. When does Croston struggle?

<details>
<summary>Show answers</summary>

1. They average the zeros in, forecasting sizes like 1.2 every period - a number that is simultaneously too big for quiet days and too small for sale days.

2. Demand size when a sale occurs, and the interval between sales - the forecast divides one by the other.

3. When demand shifts (level or frequency changes) - its slow smoothing lags regime changes.

</details>

## Try this now

Feed a sparser series ([0,0,4,0,0,0,0,6]) and verify the per-period forecast lands between the sale sizes, diluted by gaps.

---
[← Seasonal Indices](seasonal_indices.md) · [Back to Forecasting library](README.md) · [Croston with Decay →](croston_with_decay.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
