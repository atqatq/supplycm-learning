---
title: "Johnson's Rule (2-Machine Flow) | supplycm Algorithm Library"
description: "Plain-English explanation of johnsons_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, johnsons_rule, supply chain, plain english, scheduling"
---

# Johnson's Rule (2-Machine Flow)

> **Call it:** `from supplycm.scheduling import johnsons_rule` · **Level:** Intermediate · **You need:** basic arithmetic only

Two machines in sequence, many jobs: Johnson's Rule sequences them optimally. Scan for the smallest time anywhere - if it's on machine 1, schedule that job as early as possible; if on machine 2, as late as possible. Repeat. It minimizes the total makespan exactly, every time.

**Think of it like this:** A car wash with wash and dry stages: you want no car waiting wet and no dryer idle - Johnson found the perfect lineup in the 1950s.

## When to reach for it

- Any two-stage process: prep then finish, cook then package
- The exact answer for 2-machine flow shop makespan

## Try it with supplycm

```python
from supplycm.scheduling import johnsons_rule

result = johnsons_rule(jobs=[(3, 2), (4, 1), (2, 3)])
print(result)
```

You should see something like:

```text
[2, 0, 1]
```

Optimal order [2, 0, 1] - jobs with small second-machine times go last, keeping the second machine fed without starving it.

## Check yourself

1. What's the rule for the smallest time found?
2. What does Johnson minimize exactly?
3. Why does machine 2 matter most?

<details>
<summary>Show answers</summary>

1. If it belongs to machine 1, schedule that job from the FRONT; machine 2 times fill from the BACK.

2. Makespan for 2-machine flow shops - total completion of everything, optimally.

3. It's the bottleneck risk: keep it continuously busy and nothing waits at the end - that's the whole insight.

</details>

## Try this now

Schedule 5 jobs through wash/dry by hand with Johnson; compute makespan before and after vs FCFS.

---
[← Total Weighted Tardiness](total_weighted_tardiness.md) · [Back to Scheduling library](README.md) · [Flow Shop Schedule →](flow_shop_schedule.md)
