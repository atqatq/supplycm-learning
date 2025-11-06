---
title: "Pegels Classification | supplycm Algorithm Library"
description: "Plain-English explanation of pegels_classification from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, pegels_classification, supply chain, plain english, forecasting"
---

# Pegels Classification

> **Call it:** `from supplycm.forecasting import pegels_classification` · **Level:** Intermediate · **You need:** basic arithmetic only

Before choosing an exponential smoothing model, CLASSIFY your data: does it have error structure, trend, season? Pegels returns a compact code like 'ANN' (no trend, no season) or 'AAM' (additive trend, multiplicative season) - the map that picks the right smoothing engine for you.

**Think of it like this:** A doctor's triage before prescribing: symptoms first (trend? season?), then the right medicine - not the other way around.

## When to reach for it

- Choosing between SES, Holt, and Holt-Winters objectively
- Automating model selection across hundreds of SKUs

## Try it with supplycm

```python
from supplycm.forecasting import pegels_classification

result = pegels_classification([10, 12, 14, 16, 20, 25, 30, 36])
print(result)
```

You should see something like:

```text
'ANN'
```

'ANN' style codes come back - letters spell out error, trend, and season structure; each letter combination maps to one smoothing method.

## Check yourself

1. What do the three letters describe?
2. Series classified 'AAN' - which method fits?
3. Why classify at all instead of always using Holt-Winters?

<details>
<summary>Show answers</summary>

1. Error type, trend type, season type - each 'A' (additive), 'M' (multiplicative), or 'N' (none).

2. Holt's linear trend - additive trend, no seasonality.

3. Fit without structure is noise-fitting - simpler matched models are more stable and just as accurate.

</details>

## Try this now

Classify a trending seasonal series and verify the code sends you to Holt-Winters; then classify a flat noisy one.

---
[← TSB Method](tsb_method.md) · [Back to Forecasting library](README.md) · [Linear Regression Forecast →](linear_regression_forecast.md)
