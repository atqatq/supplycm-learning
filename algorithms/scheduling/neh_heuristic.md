---
title: "NEH Heuristic | supplycm Algorithm Library"
description: "Plain-English explanation of neh_heuristic from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, neh_heuristic, supply chain, plain english, scheduling"
---

# NEH Heuristic

> **Call it:** `from supplycm.scheduling import neh_heuristic` · **Level:** Advanced · **You need:** basic arithmetic only

The strongest practical heuristic for multi-machine flow shops: sort jobs by total workload (biggest first), then insert each into the position that minimizes makespan given jobs already placed. Simple recipe, remarkably strong results - the community favorite for decades.

**Think of it like this:** Building a football team: draft the best players first (total workload), and slot each new star where the team plays best - greedy with taste.

## When to reach for it

- 3+ machine flow shops where near-optimal beats exact-but-slow
- The go-to seed for further improvement methods

## Try it with supplycm

```python
from supplycm.scheduling import neh_heuristic

result = neh_heuristic(processing_times=[[3, 2, 2], [4, 1, 3], [2, 3, 1]])
print(result)
```

You should see something like:

```text
[2, 0, 1]
```

A near-optimal order - typically within a few percent of the best possible for flow shop makespan.

## Check yourself

1. What are NEH's two phases?
2. Why does 'biggest first' work as insertion order?
3. NEH vs Johnson's Rule - when each?

<details>
<summary>Show answers</summary>

1. Sort jobs by total processing (descending), then insert each greedily at its best position.

2. Big jobs constrain the schedule most - placing them early prevents late regret.

3. Johnson: exactly 2 machines, provably optimal. NEH: 3+ machines, no optimality promise but excellent in practice.

</details>

## Try this now

Run NEH on a 4-job, 3-machine instance; compare its makespan with FCFS and with random restarts you try by hand.

---
[← Flow Shop Schedule](flow_shop_schedule.md) · [Back to Scheduling library](README.md) · [Makespan (Cmax) Calculation →](cmax_calculation.md)
