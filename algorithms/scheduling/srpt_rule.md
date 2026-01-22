---
title: "SRPT (Shortest Remaining Processing Time) | supplycm Algorithm Library"
description: "Plain-English explanation of srpt_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, srpt_rule, supply chain, plain english, scheduling"
---

# SRPT (Shortest Remaining Processing Time)

> **Call it:** `from supplycm.scheduling import srpt_rule` · **Level:** Intermediate · **You need:** basic arithmetic only

SPT that re-evaluates constantly: whenever a new job arrives or a shorter remaining time appears, the machine switches to whoever has the LEAST work left. It is provably optimal for average flow time with arrivals - the most responsive rule in the book.

**Think of it like this:** A chef who pauses the stew the moment a quick omelette order comes in - always cooking whatever finishes soonest, given everything on the stove.

## When to reach for it

- Shops where jobs arrive while work is in progress
- Systems where average response time is the KPI

## Try it with supplycm

```python
from supplycm.scheduling import srpt_rule

result = srpt_rule(remaining_times=[8, 3, 5])
print(result)
```

You should see something like:

```text
1
```

The index of the job with least remaining work - call it at every decision point and the average wait bottoms out.

## Check yourself

1. How does SRPT differ from plain SPT?
2. What's SRPT's cost?
3. Why is it optimal for average flow time?

<details>
<summary>Show answers</summary>

1. SPT decides once at the start; SRPT re-decides at every completion AND considers partial progress.

2. Context switching and starvation of big jobs - the same SPT trade-off, sharpened by preemption.

3. Finishing anything sooner unblocks the queue sooner - greedily minimizing the next finish dominates, provably.

</details>

## Try this now

Mid-job, a tiny job arrives under SPT vs SRPT - trace both policies' next moves and total waiting difference.

---
[← List Scheduling](list_scheduling.md) · [Back to Scheduling library](README.md) · [Preemptive SPT (Flow Time) →](preemptive_spt.md)
