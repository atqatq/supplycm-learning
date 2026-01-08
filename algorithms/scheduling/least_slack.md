---
title: "Least Slack (LS) | supplycm Algorithm Library"
description: "Plain-English explanation of least_slack from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, least_slack, supply chain, plain english, scheduling"
---

# Least Slack (LS)

> **Call it:** `from supplycm.scheduling import least_slack` · **Level:** Intermediate · **You need:** basic arithmetic only

Slack = time remaining minus work remaining. The job with the LEAST slack is closest to doom relative to its workload - serve it first. It ignores due dates per se and focuses on the countdown: how many free minutes remain before trouble.

**Think of it like this:** Air traffic control: the plane with least reserve fuel lands first - regardless of its scheduled slot.

## When to reach for it

- Mixed job sets where due dates and workloads vary independently
- Dynamic dispatching where simplicity beats optimality

## Try it with supplycm

```python
from supplycm.scheduling import least_slack

result = least_slack(processing_times=[4, 2, 8], due_dates=[10, 4, 20], current_time=2)
print(result)
```

You should see something like:

```text
[1, 0, 2]
```

Slack per job, smallest first - negative slack means trouble already; the queue attacks the thinnest margins first.

## Check yourself

1. How does slack differ from critical ratio?
2. When do LS and EDD agree?
3. What's LS's blind spot?

<details>
<summary>Show answers</summary>

1. Slack subtracts (time - work); CR divides - slack is absolute, CR is relative; they reorder differently.

2. When jobs' workloads are similar - then slack ordering collapses to due-date ordering.

3. It ignores job VALUE - a 5-minute-urgent trivial job outranks a massive revenue job with slightly more slack.

</details>

## Try this now

Set current_time to 8 on the example; identify which jobs now have negative slack and what that means operationally.

---
[← Critical Ratio (CR)](critical_ratio.md) · [Back to Scheduling library](README.md) · [Moore-Hodgson Algorithm →](moore_hodgson.md)
