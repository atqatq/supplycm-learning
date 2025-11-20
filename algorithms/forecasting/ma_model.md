---
title: "MA Model (Moving Average Process) | supplycm Algorithm Library"
description: "Plain-English explanation of ma_model from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, ma_model, supply chain, plain english, forecasting"
---

# MA Model (Moving Average Process)

> **Call it:** `from supplycm.forecasting import ma_model` · **Level:** Advanced · **You need:** basic arithmetic only

Not the moving-average FORECAST - the statistical MA model: today's value = base level plus weighted recent SHOCKS (surprises). It models how unexpected jolts echo through a series and fade. Fitted coefficients reveal how long a demand surprise lingers.

**Think of it like this:** A pond after a stone: the ripple (shock) affects the surface for a few moments, then fades - MA models the ripple, not the water's depth.

## When to reach for it

- Modeling how demand shocks propagate and die out
- Building blocks toward ARMA-style understanding

## Try it with supplycm

```python
from supplycm.forecasting import ma_model

result = ma_model([100, 104, 101, 103, 100, 102, 101], q=1)
print(result)
```

You should see something like:

```text
[[0.4623], 1.5404]
```

A shock coefficient and base level - the modest coefficient says surprises here fade quickly rather than compounding.

## Check yourself

1. What is a 'shock' in MA language?
2. MA model vs moving-average forecast - totally different?
3. What does a large MA coefficient mean operationally?

<details>
<summary>Show answers</summary>

1. The unexpected part of a period - actual minus what the base process predicted.

2. Yes - one is a statistical model of shock propagation; the other is a forecasting heuristic. Same words, different universes.

3. Surprises linger - a promotional spike keeps echoing; plan buffers accordingly.

</details>

## Try this now

Fit MA(1) to a calm series, then to one with a big one-period spike; compare coefficients and narrate the echo.

---
[← AR Model (Autoregressive)](ar_model.md) · [Back to Forecasting library](README.md) · [VAR Model (Vector Autoregression) →](var_model.md)
