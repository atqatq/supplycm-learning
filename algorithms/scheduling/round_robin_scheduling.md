---
title: "Round-Robin Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of round_robin_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, round_robin_scheduling, supply chain, plain english, scheduling"
---

# Round-Robin Scheduling

> **Call it:** `from supplycm.scheduling import round_robin_scheduling` · **Level:** Intermediate · **You need:** basic arithmetic only

Every job gets a fixed time slice in turn - everyone shares, nobody hogs. Completion times come out fair and predictable; throughput pays a little for the switching. The default fairness engine of operating systems and call centers alike.

**Think of it like this:** Kids sharing one gaming console in 15-minute shifts - everyone plays, nobody waits the whole afternoon, and the timer keeps peace.

## When to reach for it

- Fair-sharing limited capacity across many jobs
- Service desks where no request may wait too long

## Try it with supplycm

```python
from supplycm.scheduling import round_robin_scheduling

result = round_robin_scheduling(arrival_times=[0, 0, 1], processing_times=[5, 3, 4], quantum=2)
print(result)
```

You should see something like:

```text
[12.0, 9.0, 11.0]
```

Completion times per job - much closer together than FCFS would give; that's fairness, purchased with switching overhead.

## Check yourself

1. What does the quantum control?
2. Why do completion times converge under round-robin?
3. When is round-robin the wrong choice?

<details>
<summary>Show answers</summary>

1. Slice size: tiny quanta maximize fairness but add switching overhead; large quanta drift toward FCFS behavior.

2. Everyone advances in parallel - nobody finishes early, but nobody waits forever either.

3. When variance matters more than fairness - tight due dates prefer priority rules over equal slices.

</details>

## Try this now

Compare round-robin vs FCFS completion-time spread for [10, 1, 1]; visualize the fairness difference.

---
[← Preemptive SPT (Flow Time)](preemptive_spt.md) · [Back to Scheduling library](README.md) · [Parallel Machine Makespan →](parallel_machine_cmax.md)
