---
title: "EDD (Earliest Due Date) | supplycm Algorithm Library"
description: "Plain-English explanation of edd_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, edd_rule, supply chain, plain english, scheduling"
---

# EDD (Earliest Due Date)

> **Call it:** `from supplycm.scheduling import edd_rule` · **Level:** Beginner · **You need:** basic arithmetic only

Serve whoever is due soonest. EDD provably minimizes the MAXIMUM lateness - no job will be later than it has to be. It won't minimize average waiting, but it caps the worst embarrassment, which is often what customers actually feel.

**Think of it like this:** Paying bills in order of due dates: the mortgage before the streaming service - disasters prevented, not averages optimized.

## When to reach for it

- Deadline-driven environments with penalty clauses
- Any 'no job should be catastrophically late' priority

## Try it with supplycm

```python
from supplycm.scheduling import edd_rule

result = edd_rule(due_dates=[7, 3, 10, 5])
print(result)
```

You should see something like:

```text
[1, 3, 0, 2]
```

Order by promise date: job 2 (due 3) first, job 1 (due 7) last - the worst-case lateness shrinks to its minimum.

## Check yourself

1. What does EDD provably minimize?
2. EDD vs SPT conflict - when does each win the argument?
3. How do you combine both instincts?

<details>
<summary>Show answers</summary>

1. Maximum lateness - the single worst lateness any job suffers.

2. EDD when penalties explode for the latest job; SPT when average service time rules.

3. Composite rules (like critical ratio) blend due-date urgency with processing need - EDD and SPT are its two extremes.

</details>

## Try this now

For jobs with due dates [5, 5, 5, 20], compare EDD and SPT on max lateness vs average flow time.

---
[← WSPT (Weighted SPT)](wspt_rule.md) · [Back to Scheduling library](README.md) · [Critical Ratio (CR) →](critical_ratio.md)
