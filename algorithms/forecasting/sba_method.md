---
title: "SBA (Syntetos-Boylan Approximation) | supplycm Algorithm Library"
description: "Plain-English explanation of sba_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, sba_method, supply chain, plain english, forecasting"
---

# SBA (Syntetos-Boylan Approximation)

> **Call it:** `from supplycm.forecasting import sba_method` · **Level:** Intermediate · **You need:** basic arithmetic only

Croston's method quietly OVER-forecasts intermittent demand by about the interval size. SBA applies a simple correction factor (1 minus half the smoothing parameter) that removes most of the bias - the same two components, honestly resized.

**Think of it like this:** A scale that's known to read 5% heavy: same weighing, minus the famous correction - better decisions from the same data.

## When to reach for it

- Intermittent spare parts where inventory depends on the forecast level
- Any Croston use case - SBA is usually the better default

## Try it with supplycm

```python
from supplycm.forecasting import sba_method

result = sba_method([2, 0, 0, 5, 0, 3, 0, 0], alpha=0.2, beta=0.2)
print(result)
```

You should see something like:

```text
[1.8, 1.8, 1.8, 1.6714, 1.6714, 1.5868, 1.5868, 1.5868]
```

Forecasts land slightly BELOW Croston's - the bias correction at work; over a year of ordering, that gap is real money.

## Check yourself

1. What bias does Croston have?
2. How big is SBA's correction?
3. Why do stock policies care so much about this bias?

<details>
<summary>Show answers</summary>

1. It forecasts the size/interval ratio, which overstates average demand per period by roughly the interval's worth.

2. The forecast shrinks by a factor tied to alpha - at typical alphas, roughly 10-15% lower than Croston.

3. Safety stock and order quantities multiply the forecast - a 12% level bias becomes a 12% inventory bias, item after item.

</details>

## Try this now

Run Croston and SBA on the same intermittent series; sum the 12-period forecasts and express the difference in units.

---
[← Croston with Decay](croston_with_decay.md) · [Back to Forecasting library](README.md) · [TSB Method →](tsb_method.md)
