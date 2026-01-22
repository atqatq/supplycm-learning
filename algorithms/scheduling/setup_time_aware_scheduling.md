---
title: "Setup-Time-Aware Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of setup_time_aware_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, setup_time_aware_scheduling, supply chain, plain english, scheduling"
---

# Setup-Time-Aware Scheduling

> **Call it:** `from supplycm.scheduling import setup_time_aware_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Real machines pay a changeover between DIFFERENT jobs - and the cost depends on the pair (red to blue: quick; red to black: an hour). This sequences jobs respecting a setup matrix, choosing an order that minimizes total changeover pain.

**Think of it like this:** A painter's day: going light-to-dark needs less cleaning between colors - the sequence, not the speed, saves the afternoon.

## When to reach for it

- Paint, printing, food, injection molding - any family-switching costs
- Squeezing capacity out of setup-dominated machines

## Try it with supplycm

```python
from supplycm.scheduling import setup_time_aware_scheduling

result = setup_time_aware_scheduling(processing_times=[3, 2, 4], setup_matrix=[[0, 1, 2], [1, 0, 1], [2, 1, 0]])
print(result)
```

You should see something like:

```text
[0, 1, 2]
```

A sequence chosen with setups in mind - total time now includes changeovers; compare with an oblivious order to see the waste.

## Check yourself

1. Why does job ORDER change total setup cost?
2. What problem does this secretly resemble?
3. How does SMED interact with this?

<details>
<summary>Show answers</summary>

1. Setups depend on consecutive PAIRS - sequencing similar jobs together makes most setups cheap or zero.

2. The Traveling Salesman Problem - cities are jobs, distances are setup times; that's why it's hard and heuristics matter.

3. They multiply: cheaper setups (SMED) make sequencing less critical; big setups make sequencing a gold mine.

</details>

## Try this now

Sum setups for the given order vs a sorted-similar order on a 5-job matrix; convert the saving into machine-hours per week.

---
[← Batch Scheduling](batch_scheduling.md) · [Back to Scheduling library](README.md) · [No-Wait Scheduling →](no_wait_scheduling.md)
