---
title: "MASE (Mean Absolute Scaled Error) | supplycm Algorithm Library"
description: "Plain-English explanation of mase from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mase, supply chain, plain english, statistics & accuracy"
---

# MASE (Mean Absolute Scaled Error)

> **Call it:** `from supplycm.statistics import mase` · **Level:** Advanced · **You need:** basic arithmetic only

MASE compares your forecast against the naive 'copy yesterday' forecast. Below 1.0 means you beat the lazy baseline; above 1.0 means your fancy method is worse than copying. It works across products of any scale, which makes it a favorite of forecasting researchers.

**Think of it like this:** A personal-best benchmark: the question is not your time, but whether you beat your own previous record.

## When to reach for it

- Honestly answering 'is our model better than the simple baseline?'
- Comparing accuracy across products with different scales

## Try it with supplycm

```python
from supplycm.statistics import mase

result = mase([100, 110, 120, 130, 140], [102, 112, 122, 132, 142], seasonal=1)
print(result)
```

You should see something like:

```text
0.2
```

Well below 1.0 - this forecast comfortably beats just copying the previous value, so it is earning its keep.

## Check yourself

1. MASE of 1.4 means what?
2. Why is MASE called 'scaled'?
3. Your MAPE looks great but MASE is 1.2. Trust which one?

<details>
<summary>Show answers</summary>

1. Your method is 40% worse than the naive baseline - time to simplify or re-fit.

2. The errors are divided by the naive method's typical error, stripping out product scale.

3. Be suspicious - relative to its own history, the forecast is losing to 'copy yesterday'. MASE catches that trap.

</details>

## Try this now

Forecast a trending series with the naive method vs a 3-week moving average; confirm MASE shows which wins.

---
[← Percent Bias (PBIAS)](percent_bias.md) · [Back to Statistics & Accuracy library](README.md) · [Forecast Value Added (FVA) →](forecast_value_added.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
