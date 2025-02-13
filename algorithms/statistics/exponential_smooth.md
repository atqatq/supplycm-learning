---
title: "Exponential Smoothing (Statistics) | supplycm Algorithm Library"
description: "Plain-English explanation of exponential_smooth from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, exponential_smooth, supply chain, plain english, statistics & accuracy"
---

# Exponential Smoothing (Statistics)

> **Call it:** `from supplycm.statistics import exponential_smooth` · **Level:** Beginner · **You need:** basic arithmetic only

This smoother weights recent points more than old ones, with alpha controlling the memory: high alpha = reactive, low alpha = calm. Unlike a moving average it never 'runs out' of history - older points just fade away gradually. It is the workhorse behind many demand planners.

**Think of it like this:** Your impression of a friend's mood: dominated by how they acted today, with older days still faintly counting.

## When to reach for it

- Cleaning noisy demand while staying responsive to recent shifts
- As the level engine inside bigger forecasting methods

## Try it with supplycm

```python
from supplycm.statistics import exponential_smooth

result = exponential_smooth([40, 60, 40, 60, 40], alpha=0.3)
print(result)
```

You should see something like:

```text
[40.0, 46.0, 44.2, 48.94, 46.258]
```

With alpha 0.3 the smoothed line wobbles much less than the raw data - recent values pull it only gently.

## Check yourself

1. What does alpha = 0.9 vs alpha = 0.1 change?
2. Why is it called 'exponential'?
3. You notice a level shift last week. Should alpha go up or down?

<details>
<summary>Show answers</summary>

1. 0.9 chases recent points closely (jumpy); 0.1 changes slowly (smooth but laggy).

2. The weights on older points shrink by a constant factor each step back, decaying exponentially.

3. Up - more weight on recent data lets the smoother catch up faster.

</details>

## Try this now

Smooth one series with alpha 0.2 and 0.8; identify which version would have warned you sooner of a demand jump.

---
[← Moving Average Smoothing](moving_average_smooth.md) · [Back to Statistics & Accuracy library](README.md) · [ANOVA (One-Way F-Statistic) →](anova_one_way.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
