---
title: "Croston with Decay | supplycm Algorithm Library"
description: "Plain-English explanation of croston_with_decay from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, croston_with_decay, supply chain, plain english, forecasting"
---

# Croston with Decay

> **Call it:** `from supplycm.forecasting import croston_with_decay` · **Level:** Advanced · **You need:** basic arithmetic only

Croston with a twist for fading products: a decay factor progressively shrinks the forecast when sales keep not happening. Standard Croston keeps forecasting the old average forever; the decay version gently lowers expectations as a part dies.

**Think of it like this:** A regular customer who stopped showing up: you don't keep prepping their usual order forever - each absent week lowers your expectation a notch.

## When to reach for it

- Phasing-out spares and end-of-life products
- Intermittent demand where disappearance is a real possibility

## Try it with supplycm

```python
from supplycm.forecasting import croston_with_decay

result = croston_with_decay([2, 0, 0, 5, 0, 3, 0, 0, 0, 0], alpha=0.2, decay=0.95)
print(result)
```

You should see something like:

```text
[2, 1.9, 1.805, 2.444, 2.3218, 2.4574, 2.3346, 2.2178, 2.1069, 2.0016]
```

The forecast path sags as trailing zeros accumulate - standard Croston would flatline at the old average; decay bends it down.

## Check yourself

1. What does the decay factor control?
2. Why does plain Croston over-forecast dying products?
3. What's the danger of too much decay?

<details>
<summary>Show answers</summary>

1. How fast expectations shrink during sales droughts - 0.95 drifts down gently, 0.8 gives up quickly.

2. It anchors on the historical average size and interval, blind to the fact that demand is leaving.

3. Killing forecasts for parts that come back - a big dormant contract sale would look 'dead' right before it returns.

</details>

## Try this now

Compare plain Croston vs decay-Croston on a series that goes silent after period 8; quantify the gap at period 12.

---
[← Croston's Method](crostons_method.md) · [Back to Forecasting library](README.md) · [SBA (Syntetos-Boylan Approximation) →](sba_method.md)
