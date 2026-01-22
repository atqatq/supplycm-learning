---
title: "Parallel Station Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of parallel_station_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, parallel_station_scheduling, supply chain, plain english, scheduling"
---

# Parallel Station Scheduling

> **Call it:** `from supplycm.scheduling import parallel_station_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Like parallel machines, but arrivals matter: jobs SHOW UP over time and stations serve first-come with any free station. This simulates that flow and returns per-station assignments - the reality of checkouts, exam rooms, and loading bays.

**Think of it like this:** A bank with three windows and a stream of arriving customers: each arrival goes to whichever window opens next.

## When to reach for it

- Stations serving arriving work (docks, clinics, support)
- Sizing how many stations a given arrival pattern needs

## Try it with supplycm

```python
from supplycm.scheduling import parallel_station_scheduling

result = parallel_station_scheduling(arrival_times=[0, 1, 2, 3], processing_times=[4, 3, 2, 5], num_stations=2)
print(result)
```

You should see something like:

```text
[[0, 2], [1, 3]]
```

Per-station job lists - trace each arrival to its station and note where queues formed anyway.

## Check yourself

1. What drives waiting here?
2. How do you decide the number of stations?
3. When do more stations NOT help?

<details>
<summary>Show answers</summary>

1. Arrival bunching: when several arrive before any station frees, queues form - no rule avoids physics.

2. Simulate candidates: adds stations until waiting (and its cost) stops justifying the station cost.

3. When arrivals are sparse - idle stations cost money without removing any wait that exists.

</details>

## Try this now

Re-run with 3 stations; find the arrival that still waited and decide if a third station was worth it.

---
[← Parallel Machine Makespan](parallel_machine_cmax.md) · [Back to Scheduling library](README.md) · [Multifit Algorithm →](multifit_algorithm.md)
