---
title: "PERT Expected Duration | supplycm Algorithm Library"
description: "Plain-English explanation of pert_expected_duration from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, pert_expected_duration, supply chain, plain english, scheduling"
---

# PERT Expected Duration

> **Call it:** `from supplycm.scheduling import pert_expected_duration` · **Level:** Intermediate · **You need:** basic arithmetic only

Single-point estimates lie. PERT asks for three - optimistic, most likely, pessimistic - and blends them into an expected duration (with a variance). The expected time skews toward the optimistic side, which is exactly why projects keep surprising us.

**Think of it like this:** Estimating a bike ride: best case 30 min, usual 40, headwind disaster 80 - the blend says 'plan for 45, and know why'.

## When to reach for it

- Project estimates under genuine uncertainty
- Sanity-checking single-number estimates that feel too confident

## Try it with supplycm

```python
from supplycm.scheduling import pert_expected_duration

result = pert_expected_duration(optimistic=[1, 2, 3], most_likely=[2, 3, 4], pessimistic=[3, 4, 5])
print(result)
```

You should see something like:

```text
[[2.0, 0.1111], [3.0, 0.1111], [4.0, 0.1111]]
```

Expected duration and variance per task - feed the durations into CPM and you have PERT-project scheduling end to end.

## Check yourself

1. What's the standard PERT blend?
2. Why does the expected value skew low?
3. What does the variance tell you?

<details>
<summary>Show answers</summary>

1. (Optimistic + 4 x most likely + pessimistic) / 6 - a weighted bet that reality sits near 'most likely'.

2. The formula weights 'most likely' four-fold - distributions with long pessimistic tails still average below their worst case.

3. Estimate confidence - high-variance tasks deserve buffers and watching, not just planning.

</details>

## Try this now

Give one task a huge pessimistic estimate and watch its variance explode - explain to a PM what that signals.

---
[← Slack Time Calculation](slack_time_calculation.md) · [Back to Scheduling library](README.md) · [RPW Priority (Ranked Positional Weight) →](rpw_priority.md)
