---
title: "FCFS (First Come, First Served) | supplycm Algorithm Library"
description: "Plain-English explanation of fcfs_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, fcfs_rule, supply chain, plain english, scheduling"
---

# FCFS (First Come, First Served)

> **Call it:** `from supplycm.scheduling import fcfs_rule` · **Level:** Beginner · **You need:** basic arithmetic only

Serve jobs in arrival order - the queue at the bakery counter. Zero judgment required, perfectly fair in appearance, and hopeless when a 2-minute job hides behind a 2-hour one. The default rule of the universe, and the baseline every other rule must beat.

**Think of it like this:** The supermarket single line: whoever arrived first checks out first, whatever their basket holds.

## When to reach for it

- Fairness is contractual or cultural
- The baseline for judging smarter sequencing rules

## Try it with supplycm

```python
from supplycm.scheduling import fcfs_rule

result = fcfs_rule(arrival_times=[0, 5, 2, 8, 3])
print(result)
```

You should see something like:

```text
[0, 2, 4, 1, 3]
```

Jobs ordered by arrival - the early birds first; watch how one slow early job delays everyone behind it.

## Check yourself

1. What is FCFS's biggest operational weakness?
2. When is FCFS genuinely the right rule?
3. Why keep FCFS as a benchmark?

<details>
<summary>Show answers</summary>

1. Long jobs block short ones - average waiting time balloons when a monster job arrives early.

2. When arrival order IS the promise (service counters) or when switching costs punish cleverness.

3. It quantifies what smarter rules buy you - the gap is the value of scheduling itself.

</details>

## Try this now

Schedule [2, 40, 3] minutes of jobs by FCFS; compute total waiting time, then find the rule that halves it.

---
[Back to Scheduling library](README.md) · [SPT (Shortest Processing Time) →](spt_rule.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
