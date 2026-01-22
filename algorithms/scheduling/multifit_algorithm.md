---
title: "Multifit Algorithm | supplycm Algorithm Library"
description: "Plain-English explanation of multifit_algorithm from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, multifit_algorithm, supply chain, plain english, scheduling"
---

# Multifit Algorithm

> **Call it:** `from supplycm.scheduling import multifit_algorithm` · **Level:** Advanced · **You need:** basic arithmetic only

A clever twist on parallel scheduling: binary-search the SMALLEST machine capacity that fits all jobs (like bin packing), then declare that capacity the makespan candidate. Packing feasibility becomes the measuring stick - usually landing within a few percent of optimal.

**Think of it like this:** Choosing the smallest truck that can hold everything: too small fails the trial load, too big wastes fuel - binary search finds the tipping point.

## When to reach for it

- Makespan minimization where clever beats greedy
- Sizing capacity questions (how big must each machine be?)

## Try it with supplycm

```python
from supplycm.scheduling import multifit_algorithm

result = multifit_algorithm(processing_times=[4, 3, 5, 2], num_machines=2, iterations=10)
print(result)
```

You should see something like:

```text
[[2, 3], [0, 1]]
```

The makespan found by capacity search - compare with LPT's answer on the same instance; the search usually edges it.

## Check yourself

1. What is being binary-searched?
2. Why connect scheduling to bin packing?
3. What's multifit's guarantee?

<details>
<summary>Show answers</summary>

1. Machine capacity: can all jobs pack into k machines of capacity C? Shrink C until packing barely fails.

2. Identical machines + makespan C = pack all jobs into bins of size C - the problems are twins.

3. Within about 1.2 of optimal - stronger than LPT's guarantee, at slightly more computation.

</details>

## Try this now

Run multifit and LPT on [7, 6, 5, 4, 3] with 3 machines; find the instance where they disagree and judge the winner.

---
[← Parallel Station Scheduling](parallel_station_scheduling.md) · [Back to Scheduling library](README.md) · [Batch Scheduling →](batch_scheduling.md)
