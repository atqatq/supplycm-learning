---
title: "Resource-Constrained Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of resource_constrained_scheduling from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, resource_constrained_scheduling, supply chain, plain english, scheduling"
---

# Resource-Constrained Scheduling

> **Call it:** `from supplycm.scheduling import resource_constrained_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Project scheduling's reality check: tasks need PEOPLE and machines, and there aren't enough. This schedules tasks respecting both precedence AND resource capacity - finish times stretch beyond the pure critical path, and the stretch is the honest answer.

**Think of it like this:** Dinner for twelve with one oven: recipe order (precedence) is one thing - the oven (resource) is what actually sets the serving time.

## When to reach for it

- Real project plans where staff/equipment are finite
- Explaining to stakeholders why 'CPM says 10 days' became 14

## Try it with supplycm

```python
from supplycm.scheduling import resource_constrained_scheduling

result = resource_constrained_scheduling(durations=[3, 2, 4], successors=[[1], [], []], resource_demands=[[1], [1], [1]], resource_capacities=[2])
print(result)
```

You should see something like:

```text
[0, 3.0, 0]
```

Start times under capacity - compare with the unconstrained earliest-start schedule and measure the delay capacity forced.

## Check yourself

1. What does adding resources do to the CPM result?
2. Where's the first place to look when schedules slip?
3. What's the classic remedy toolbox?

<details>
<summary>Show answers</summary>

1. Dates stretch whenever tasks compete for the same limited pool - critical paths shift dynamically.

2. Resource contention peaks - periods where demand exceeds capacity; level or add there.

3. Split or shuffle flexible tasks (use their slack), add capacity briefly, or re-sequence - in that order of cheapness.

</details>

## Try this now

Tighten capacity to 1 on the example; watch both tasks queue and compare the finish date with CPM's promise.

---
[← Learning Curve Scheduling](learning_curve_scheduling.md) · [Back to Scheduling library](README.md) · [LRPT (Longest Remaining Processing Time) →](lrpt_rule.md)
