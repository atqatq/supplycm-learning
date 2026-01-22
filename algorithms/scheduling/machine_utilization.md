---
title: "Machine Utilization | supplycm Algorithm Library"
description: "Plain-English explanation of machine_utilization from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, machine_utilization, supply chain, plain english, scheduling"
---

# Machine Utilization

> **Call it:** `from supplycm.scheduling import machine_utilization` · **Level:** Beginner · **You need:** basic arithmetic only

The simplest health metric in operations: busy time divided by available time, per machine. High utilization means money-making work; 100% means zero slack for surprises. This computes it from loads and the schedule's makespan.

**Think of it like this:** Occupancy rate of a hotel: rooms sold over rooms available - except a 100%-full factory is a heart attack waiting for a demand spike.

## When to reach for it

- Daily operations reporting
- Diagnosing whether capacity or demand limits output

## Try it with supplycm

```python
from supplycm.scheduling import machine_utilization

result = machine_utilization(machine_loads=[8, 6, 4], makespan=10)
print(result)
```

You should see something like:

```text
[0.8, 0.6, 0.4]
```

A percentage per machine - the third machine idles nearly half the schedule; either feed it, reassign, or right-size it.

## Check yourself

1. Why is 100% utilization a warning, not a trophy?
2. How do utilization numbers guide staffing?
3. Utilization vs efficiency - difference?

<details>
<summary>Show answers</summary>

1. No buffer survives - any breakdown, rush order, or absentee has nowhere to be absorbed.

2. Persistently low machines are candidates for consolidation or reassignment; hot ones get help.

3. Utilization measures BUSY; efficiency measures productive output while busy - a machine can be 100% busy making scrap.

</details>

## Try this now

Compute utilization for 4 machines under one makespan; propose which machine's work to redistribute first.

---
[← LRPT (Longest Remaining Processing Time)](lrpt_rule.md) · [Back to Scheduling library](README.md)
