---
title: "Total Weighted Tardiness | supplycm Algorithm Library"
description: "Plain-English explanation of total_weighted_tardiness from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, total_weighted_tardiness, supply chain, plain english, scheduling"
---

# Total Weighted Tardiness

> **Call it:** `from supplycm.scheduling import total_weighted_tardiness` · **Level:** Advanced · **You need:** basic arithmetic only

Tardiness with stakes: each job's lateness multiplied by its weight (penalty, revenue, importance). The sum tells you which order costs LEAST in real consequences. No simple rule solves it perfectly - which is why it's the classic battleground for heuristics.

**Think of it like this:** Late library books where some are 50-cent novels and one is a rare manuscript - the fine total depends on which one you keep out.

## When to reach for it

- Real shops with contract penalties per job
- Evaluating heuristic schedules where jobs differ in stakes

## Try it with supplycm

```python
from supplycm.scheduling import total_weighted_tardiness

result = total_weighted_tardiness(sequence=[0, 1, 2], processing_times=[4, 2, 8], due_dates=[5, 6, 8], weights=[10, 1, 5])
print(result)
```

You should see something like:

```text
30.0
```

Weighted total for this order - swap the heavyweight job earlier and watch the total collapse; that's the whole optimization game.

## Check yourself

1. How do weights change the scheduling conversation?
2. Why no simple optimal rule here?
3. What sequence does intuition suggest?

<details>
<summary>Show answers</summary>

1. They convert lateness into money - now a 2-day slip on a key account can outweigh 10-day slips on trivia.

2. Weighted tardiness is NP-hard - even clever heuristics only approximate; simulations and local search earn their keep.

3. High-weight, soon-due jobs early - a blend of WSPT and EDD instincts, then let the metric judge.

</details>

## Try this now

Find (by trial) the order minimizing weighted tardiness for the example; then break it with a weight of 100 and re-solve.

---
[← Total Completion Time](total_completion_time.md) · [Back to Scheduling library](README.md) · [Johnson's Rule (2-Machine Flow) →](johnsons_rule.md)
