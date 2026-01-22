---
title: "Learning Curve Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of learning_curve_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, learning_curve_scheduling, supply chain, plain english, scheduling"
---

# Learning Curve Scheduling

> **Call it:** `from supplycm.scheduling import learning_curve_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Repetition makes workers faster: the 100th unit takes less than the 10th. This shrinks each job's time by a learning rate applied to its position in the sequence - front-loading repetition pays compounding dividends in later speed.

**Think of it like this:** Your tenth parallel-parked car takes half the time of your first - skill compounds, and scheduling can exploit it.

## When to reach for it

- New product ramps, new teams, repetitive onboarding
- Deciding whether to cluster similar repetitive jobs

## Try it with supplycm

```python
from supplycm.scheduling import learning_curve_scheduling

result = learning_curve_scheduling(processing_times=[10, 10, 10], learning_rate=0.9)
print(result)
```

You should see something like:

```text
[0, 1, 2]
```

Effective times shrink down the sequence - later jobs inherit faster hands; total capacity grows as the team warms up.

## Check yourself

1. What does a learning rate of 0.9 mean?
2. How should scheduling exploit learning?
3. When does the curve reset?

<details>
<summary>Show answers</summary>

1. Each doubling of repetition cuts time to 90% - a classic 90% learning curve from manufacturing history.

2. Cluster similar work early - the learned speed then applies to the many jobs that follow.

3. New product, new tooling, staff rotation - every change re-opens the expensive learning window.

</details>

## Try this now

Compute total time for 8 identical jobs at rate 0.85 - then argue for/against running them consecutively.

---
[← Deteriorating Jobs Scheduling](deteriorating_jobs_scheduling.md) · [Back to Scheduling library](README.md) · [Resource-Constrained Scheduling →](resource_constrained_scheduling.md)
