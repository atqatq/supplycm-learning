---
title: "Diebold-Mariano Test | supplycm Algorithm Library"
description: "Plain-English explanation of diebold_mariano_test from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, diebold_mariano_test, supply chain, plain english, statistics & accuracy"
---

# Diebold-Mariano Test

> **Call it:** `from supplycm.statistics import diebold_mariano_test` · **Level:** Advanced · **You need:** basic arithmetic only

Two forecasts, one winner - but is the win real or luck? The DM test compares their errors and returns a statistic: far from 0 means one forecast is genuinely better, near 0 means the difference is noise. It is the fair referee for method-vs-method contests.

**Think of it like this:** A photo finish review in racing: it checks whether the gap between two sprinters is real or just camera jitter.

## When to reach for it

- Deciding whether to switch forecasting methods based on evidence
- Settling 'my model vs your model' debates objectively

## Try it with supplycm

```python
from supplycm.statistics import diebold_mariano_test

result = diebold_mariano_test([100, 200, 300, 400], [110, 190, 310, 390], [120, 180, 320, 380])
print(result)
```

You should see something like:

```text
0.0
```

The statistic's distance from 0 tells you whether forecast 1's smaller errors are a real edge or a coin flip.

## Check yourself

1. DM near 0 means what?
2. You see DM = +3 consistently favoring model A. Action?
3. Why not just compare MAPE once and decide?

<details>
<summary>Show answers</summary>

1. The two forecasts are statistically indistinguishable - pick either, or blend them.

2. Adopt A, but keep monitoring - edges can fade as conditions change.

3. One sample can flatter either method; DM asks whether the gap would survive repeated testing.

</details>

## Try this now

Generate two forecast series, compute their MAPEs, then use DM to argue whether the difference is trustworthy.

---
[← Forecast Value Added (FVA)](forecast_value_added.md) · [Back to Statistics & Accuracy library](README.md) · [Anderson-Darling Statistic →](anderson_darling_test.md)
