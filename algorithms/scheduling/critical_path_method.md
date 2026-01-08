---
title: "Critical Path Method (CPM) | supplycm Algorithm Library"
description: "Plain-English explanation of critical_path_method from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, critical_path_method, supply chain, plain english, scheduling"
---

# Critical Path Method (CPM)

> **Call it:** `from supplycm.scheduling import critical_path_method` · **Level:** Intermediate · **You need:** basic arithmetic only

In every project there's a chain of tasks with ZERO slack - delay any of them and the whole project slips. CPM finds that chain. It tells you where attention and overtime actually matter, and where a 2-day delay costs nothing at all.

**Think of it like this:** A relay race's slowest leg chain: the baton's total time is dictated by certain legs - train those, and nothing else, to improve the result.

## When to reach for it

- Project deadline negotiations with evidence
- Deciding where crash efforts (overtime, expediting) pay off

## Try it with supplycm

```python
from supplycm.scheduling import critical_path_method

result = critical_path_method(durations=[3, 2, 4, 1], successors=[[1, 2], [], [3], []])
print(result)
```

You should see something like:

```text
[3]
```

The critical path's task indices - this chain, and only this chain, controls the project's finish date.

## Check yourself

1. What makes a task 'critical'?
2. Can there be multiple critical paths?
3. A non-critical task slips 2 days. Project impact?

<details>
<summary>Show answers</summary>

1. Zero slack: its earliest and latest feasible times coincide - any delay moves the project end.

2. Yes - parallel chains can tie; delaying any one of them delays the project.

3. None - until its slack runs out; then it becomes critical and the path shifts.

</details>

## Try this now

Find the critical path of a 7-task network with two parallel branches; verify by delaying one branch task harmlessly.

---
[← Earliest Start Schedule](earliest_start_schedule.md) · [Back to Scheduling library](README.md) · [Slack Time Calculation →](slack_time_calculation.md)
