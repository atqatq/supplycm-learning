---
title: "Batch Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of batch_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, batch_scheduling, supply chain, plain english, scheduling"
---

# Batch Scheduling

> **Call it:** `from supplycm.scheduling import batch_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Group compatible jobs to share setups: items from the same family run together and the changeover is paid once. This partitions jobs into batches under a capacity limit, pairing efficiency with the flexibility cost of waiting for your batch-mates.

**Think of it like this:** Laundry: wash all whites together and all colors together - fewer machine cycles, but someone's load always waits for the right group.

## When to reach for it

- Machines with family-dependent setups (paint, ovens, molds)
- Cutting total changeover time without fancy tooling

## Try it with supplycm

```python
from supplycm.scheduling import batch_scheduling

result = batch_scheduling(processing_times=[3, 4, 2, 5], families=[0, 0, 1, 1], batch_capacity=10)
print(result)
```

You should see something like:

```text
[[0, 1], [2, 3]]
```

Batches as job lists - same-family jobs share a run; count the setups saved versus running each job alone.

## Check yourself

1. What's the trade-off batching buys and pays?
2. When do large batches backfire?
3. How does this connect to SMED lean thinking?

<details>
<summary>Show answers</summary>

1. Fewer setups (paid) versus waiting for batch groups (cost) - jobs lose independence to gain efficiency.

2. High holding cost or urgent jobs - big batches delay individual items and stack inventory.

3. SMED shrinks setup cost itself - as setups get cheap, optimal batches shrink, and flexibility returns.

</details>

## Try this now

Split 8 jobs across 2 families into batches with capacity 12; count setups saved and estimate the waiting added.

---
[← Multifit Algorithm](multifit_algorithm.md) · [Back to Scheduling library](README.md) · [Setup-Time-Aware Scheduling →](setup_time_aware_scheduling.md)
