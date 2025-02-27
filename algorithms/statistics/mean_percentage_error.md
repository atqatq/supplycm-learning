---
title: "MPE (Mean Percentage Error) | supplycm Algorithm Library"
description: "Plain-English explanation of mean_percentage_error from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mean_percentage_error, supply chain, plain english, statistics & accuracy"
---

# MPE (Mean Percentage Error)

> **Call it:** `from supplycm.statistics import mean_percentage_error` · **Level:** Intermediate · **You need:** basic arithmetic only

MPE is like MAPE but keeps the sign, so it shows systematic percentage-level tilt: positive means under-forecasting in percent terms, negative means over-forecasting. Around zero means no consistent percentage bias. It is MAPE's direction-aware sibling.

**Think of it like this:** A compass for forecast error: it does not say how far off you are, only whether you keep leaning the same way.

## When to reach for it

- Detecting systematic over- or under-forecasting in percent terms
- Sanity check alongside MAPE in monthly reviews

## Try it with supplycm

```python
from supplycm.statistics import mean_percentage_error

result = mean_percentage_error([100, 200, 400], [110, 190, 380])
print(result)
```

You should see something like:

```text
0.0
```

A small positive number - the forecast leans slightly under the actuals overall, but no strong tilt.

## Check yourself

1. MPE near zero but MAPE high - what does that mean?
2. Why can MPE mislead with mixed big and small actuals?
3. MPE is -12%. Action?

<details>
<summary>Show answers</summary>

1. Errors are large but cancel out in direction - you are inconsistent rather than systematically tilted.

2. Small actuals produce huge percentage swings that can dominate the average.

3. Forecasts run about 12% high on average - trim plans or recalibrate the model upward on demand.

</details>

## Try this now

Construct a 6-week forecast that is always 10% high; confirm MPE lands near -10% and MAPE near +10%.

---
[← SMAPE (Symmetric MAPE)](smape.md) · [Back to Statistics & Accuracy library](README.md) · [Percent Bias (PBIAS) →](percent_bias.md)
