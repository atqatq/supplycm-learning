---
title: "No-Wait Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of no_wait_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, no_wait_scheduling, supply chain, plain english, scheduling"
---

# No-Wait Scheduling

> **Call it:** `from supplycm.scheduling import no_wait_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Some processes can't wait mid-route: steel must stay hot, chemicals must keep flowing. No-wait scheduling forces each job to move through machines back-to-back - start times are dictated by the chain, and the scheduler's freedom lives in the job ORDER.

**Think of it like this:** A relay where the baton can never touch the ground: each runner's start is locked to the previous runner's arrival - only the running order is yours to choose.

## When to reach for it

- Continuous processes: steel, plastics, chemistry, baking
- Cold-chain or freshness-constrained production

## Try it with supplycm

```python
from supplycm.scheduling import no_wait_scheduling

result = no_wait_scheduling(processing_times=[[3, 2, 2], [4, 1, 3]])
print(result)
```

You should see something like:

```text
[0, 1]
```

A job order satisfying the no-wait chain - each job's machine times abut perfectly; idle time migrates to the MACHINES, not the jobs.

## Check yourself

1. What's the core tension in no-wait systems?
2. Why does job order matter MORE here?
3. What process would explode under no-wait?

<details>
<summary>Show answers</summary>

1. Jobs refuse to wait, so all slack moves to machines - utilization absorbs what flow time refuses to.

2. Each pair of jobs has a fixed start-time offset (like a headway) - sequencing becomes choosing pairwise offsets, TSP-style.

3. Anything with a cure, dry, or hold step - forcing no-wait there either breaks physics or idles the plant.

</details>

## Try this now

Compute the pairwise offsets between two jobs in the example; verify the chosen order minimizes total machine idle.

---
[← Setup-Time-Aware Scheduling](setup_time_aware_scheduling.md) · [Back to Scheduling library](README.md) · [Deteriorating Jobs Scheduling →](deteriorating_jobs_scheduling.md)
