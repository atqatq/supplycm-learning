---
title: "Critical Ratio (CR) | supplycm Algorithm Library"
description: "Plain-English explanation of critical_ratio from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, critical_ratio, supply chain, plain english, scheduling"
---

# Critical Ratio (CR)

> **Call it:** `from supplycm.scheduling import critical_ratio` · **Level:** Intermediate · **You need:** basic arithmetic only

A blend of urgency and workload: CR = time remaining until due date divided by work remaining. Below 1 means already doomed (late no matter what); just above 1 means critical; big numbers mean relaxed. Work the smallest CR first.

**Think of it like this:** A student triaging homework: hours-left divided by hours-needed - the essay due tomorrow needing 6 hours beats the quiz needing 10 minutes.

## When to reach for it

- Dynamic shops where both due dates and workloads shift
- Dispatch lists updated through the day

## Try it with supplycm

```python
from supplycm.scheduling import critical_ratio

result = critical_ratio(processing_times=[4, 2, 8], due_dates=[10, 4, 20], current_time=2)
print(result)
```

You should see something like:

```text
[1, 0, 2]
```

Ratios per job, smallest first - below-1 jobs are flagged as already late; the shop attacks the most endangered first.

## Check yourself

1. What does CR below 1 mean?
2. Why is CR better than pure EDD in busy shops?
3. How often should CR be recomputed?

<details>
<summary>Show answers</summary>

1. The job cannot make its due date even if started now - it needs expediting or a reset promise.

2. It weighs due dates against the WORK required - a far deadline with huge workload deserves urgency too.

3. Continuously or at each dispatch - both clock and remaining work move as the day runs.

</details>

## Try this now

Recompute CRs at current_time 6 on the same jobs; watch how the priority order flips as time burns.

---
[← EDD (Earliest Due Date)](edd_rule.md) · [Back to Scheduling library](README.md) · [Least Slack (LS) →](least_slack.md)
