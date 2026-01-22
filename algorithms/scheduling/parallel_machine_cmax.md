---
title: "Parallel Machine Makespan | supplycm Algorithm Library"
description: "Plain-English explanation of parallel_machine_cmax from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, parallel_machine_cmax, supply chain, plain english, scheduling"
---

# Parallel Machine Makespan

> **Call it:** `from supplycm.scheduling import parallel_machine_cmax` · **Level:** Intermediate · **You need:** basic arithmetic only

You've assigned jobs to machines - now what's the actual finish time? This computes each machine's load and returns the makespan: the slowest machine's total. It is the immediate scoreboard for any assignment you or a heuristic proposes.

**Think of it like this:** Rowing a boat with several rowers: the boat moves at the SLOWEST rower's pace - the makespan is that rower's total burden.

## When to reach for it

- Evaluating any parallel-machine assignment
- Feeding the feedback loop: assign, score, re-assign

## Try it with supplycm

```python
from supplycm.scheduling import parallel_machine_cmax

result = parallel_machine_cmax(assignment=[[0, 2], [1, 3]], processing_times=[4, 5, 3, 6])
print(result)
```

You should see something like:

```text
11
```

The makespan of this assignment - rebalance one job and watch which machine's load (and the total) moves.

## Check yourself

1. What sets the makespan on parallel machines?
2. Why is perfect balance often impossible?
3. What's the lower bound any schedule must respect?

<details>
<summary>Show answers</summary>

1. The heaviest-loaded machine - every other machine's idle time is hidden behind it.

2. Jobs are indivisible - sums rarely tie exactly; the art is minimizing the unavoidable spread.

3. Total work divided by machines, and the biggest single job - makespan can never beat the larger of the two.

</details>

## Try this now

Try three assignments for 6 jobs on 2 machines; verify the lower bound and how close LPT got to it.

---
[← Round-Robin Scheduling](round_robin_scheduling.md) · [Back to Scheduling library](README.md) · [Parallel Station Scheduling →](parallel_station_scheduling.md)
