---
title: "Hurst Exponent | supplycm Algorithm Library"
description: "Plain-English explanation of hurst_exponent from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, hurst_exponent, supply chain, plain english, forecasting"
---

# Hurst Exponent

> **Call it:** `from supplycm.forecasting import hurst_exponent` · **Level:** Advanced · **You need:** basic arithmetic only

One number that describes a series' soul: near 0.5 means a random walk (no memory), above 0.5 means persistence (trends continue), below 0.5 means anti-persistence (moves reverse). It answers 'is this series a drifter, a follower, or a pendulum?'

**Think of it like this:** Reading a crowd: some wander randomly (0.5), some herd in one direction (>0.5), and some keep changing their collective mind (<0.5).

## When to reach for it

- Characterizing demand character before choosing methods
- Deciding whether trend-following or mean-reversion logic fits

## Try it with supplycm

```python
from supplycm.forecasting import hurst_exponent

result = hurst_exponent([100, 103, 108, 115, 124, 135, 148, 152])
print(result)
```

You should see something like:

```text
0.5
```

Above 0.5 - persistence: this series keeps going its way; trend-aware methods fit its personality.

## Check yourself

1. Hurst near 0.7 - what forecasting attitude fits?
2. Hurst near 0.3 - opposite attitude?
3. Why is 0.5 the neutral point?

<details>
<summary>Show answers</summary>

1. Persistence - trend-following logic; the past direction carries real information.

2. Mean reversion - spikes tend to reverse; lean against recent moves instead of following them.

3. It matches a random walk - the past direction carries no information about the next move.

</details>

## Try this now

Compute Hurst for a trending, a random, and an oscillating series; line up the three numbers and their personalities.

---
[← KPSS Test Statistic (Stationarity)](kpss_test.md) · [Back to Forecasting library](README.md) · [Theil's U →](theils_u.md)
