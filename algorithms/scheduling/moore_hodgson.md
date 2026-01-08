---
title: "Moore-Hodgson Algorithm | supplycm Algorithm Library"
description: "Plain-English explanation of moore_hodgson from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, moore_hodgson, supply chain, plain english, scheduling"
---

# Moore-Hodgson Algorithm

> **Call it:** `from supplycm.scheduling import moore_hodgson` · **Level:** Advanced · **You need:** basic arithmetic only

You can't make everyone happy - so minimize how MANY jobs are late. Moore-Hodgson does this optimally: walk through jobs by due date, and whenever one would be late, evict the longest job seen so far. The survivors all finish on time; the evicted few are your honest casualties.

**Think of it like this:** Overbooking a flight: keep adding passengers by departure order, and whenever the plane overflows, bump the heaviest luggage - minimize complaints, not eliminate them.

## When to reach for it

- Overloaded periods where some lateness is inevitable
- Deciding WHICH jobs to outsource, delay, or renegotiate

## Try it with supplycm

```python
from supplycm.scheduling import moore_hodgson

result = moore_hodgson(processing_times=[4, 2, 8, 1], due_dates=[5, 6, 8, 10])
print(result)
```

You should see something like:

```text
[0, 1, 3, 2]
```

A kept-set and implied late-set - the algorithm's evictions are the mathematically minimal number of late jobs.

## Check yourself

1. What exactly does Moore-Hodgson minimize?
2. Who gets evicted when a conflict appears?
3. After the algorithm, what's your negotiation list?

<details>
<summary>Show answers</summary>

1. The NUMBER of tardy jobs - not how late they are, just how many miss.

2. The longest processing job among those considered - clearing the most future time per complaint.

3. The evicted jobs - now you renegotiate their dates with evidence that keeping them would break MORE promises.

</details>

## Try this now

Run it on 6 jobs where 2 must be late; verify no other selection achieves fewer latenesses.

---
[← Least Slack (LS)](least_slack.md) · [Back to Scheduling library](README.md) · [Tardiness Calculation →](tardiness_calculation.md)
