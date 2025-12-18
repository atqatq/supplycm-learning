---
title: "Brier Score | supplycm Algorithm Library"
description: "Plain-English explanation of brier_score from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, brier_score, supply chain, plain english, forecasting"
---

# Brier Score

> **Call it:** `from supplycm.forecasting import brier_score` · **Level:** Advanced · **You need:** basic arithmetic only

Scores PROBABILITY forecasts: you said 80% chance of a stockout and it happened (or didn't) - the Brier score grades the calibration of such statements over many cases. Lower is better; 0 is perfect. It keeps forecasters honest about confidence, not just direction.

**Think of it like this:** Grading a poker player's 'I'm 70% sure' claims over a season - the score separates genuine calibration from confident noise.

## When to reach for it

- Scoring probabilistic risk statements (stockout likelihoods)
- Improving probability judgment over time

## Try it with supplycm

```python
from supplycm.forecasting import brier_score

result = brier_score(probabilities=[0.8, 0.4, 0.6], outcomes=[1, 0, 1])
print(result)
```

You should see something like:

```text
0.12
```

About 0.12 - decent calibration; recompute after adjusting statements toward honest frequencies and watch it fall.

## Check yourself

1. What kind of forecast does Brier grade?
2. Saying 50% for everything scores what?
3. Why should planners care about calibration?

<details>
<summary>Show answers</summary>

1. Probabilities of yes/no events - not quantities: '70% chance of delay', not '70 units'.

2. 0.25 always - the safe-but-useless baseline; real calibration must beat it.

3. Because decisions price in probabilities - if '90% reliable supplier' actually delivers 70%, buffers are built on fiction.

</details>

## Try this now

Score a colleague's (or your own) 10 past probability claims; compute the Brier score and one calibration lesson.

---
[← Tracking Signal](tracking_signal.md) · [Back to Forecasting library](README.md)
