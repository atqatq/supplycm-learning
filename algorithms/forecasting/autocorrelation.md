---
title: "Autocorrelation (ACF) | supplycm Algorithm Library"
description: "Plain-English explanation of autocorrelation from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, autocorrelation, supply chain, plain english, forecasting"
---

# Autocorrelation (ACF)

> **Call it:** `from supplycm.forecasting import autocorrelation` · **Level:** Intermediate · **You need:** basic arithmetic only

How strongly does the series correlate with ITSELF, shifted by 1, 2, 3... periods? Big lag-1 correlation means momentum; spikes at lag 4 or 12 expose hidden seasonality. ACF is the stethoscope that hears the rhythms your eyes miss.

**Think of it like this:** Bouncing a ball and recording how similar each bounce sounds to the one before - the echo pattern reveals the ball's nature.

## When to reach for it

- Detecting seasonality you haven't explicitly modeled
- Diagnosing whether a series is momentum-driven or random

## Try it with supplycm

```python
from supplycm.forecasting import autocorrelation

result = autocorrelation([10, 20, 15, 40, 12, 21, 16, 41, 11, 20, 15, 39], max_lag=6)
print(result)
```

You should see something like:

```text
[1.0, -0.4465, 0.143, -0.5277, 0.664, -0.2599, 0.086]
```

A pronounced spike at lag 4 - the seasonal cycle length shows itself in the correlation pattern, even though the raw numbers look chaotic.

## Check yourself

1. What does a high lag-1 autocorrelation mean?
2. How does ACF reveal season length?
3. ACF fades slowly with no spikes - diagnosis?

<details>
<summary>Show answers</summary>

1. Persistence: high days follow high days - momentum that smoothing methods can exploit.

2. Correlation peaks at the cycle distance - a lag-12 spike in monthly data whispers 'yearly'.

3. Trend or a random walk - the series needs differencing or trend handling before further modeling.

</details>

## Try this now

Compute ACF on 24 months of data with a yearly cycle; find the lag of the biggest spike and defend it as the season length.

---
[← VAR Model (Vector Autoregression)](var_model.md) · [Back to Forecasting library](README.md) · [Partial Autocorrelation (PACF) →](partial_autocorrelation.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
