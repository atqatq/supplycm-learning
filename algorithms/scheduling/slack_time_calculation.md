---
title: "Slack Time Calculation | supplycm Algorithm Library"
description: "Plain-English explanation of slack_time_calculation from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, slack_time_calculation, supply chain, plain english, scheduling"
---

# Slack Time Calculation

> **Call it:** `from supplycm.scheduling import slack_time_calculation` · **Level:** Intermediate · **You need:** basic arithmetic only

Slack is each task's free delay allowance: how late it can start without moving the project's finish. The function returns earliest and latest start times per task - the difference is your negotiating room with reality.

**Think of it like this:** Airport buffers: the taxi has 40 minutes of slack, security 10 - you know exactly where the schedule can bend.

## When to reach for it

- Resource leveling: shift flexible tasks off peak days
- Answering 'how late can this start?' with confidence

## Try it with supplycm

```python
from supplycm.scheduling import slack_time_calculation

result = slack_time_calculation(durations=[3, 2, 4], successors=[[1], [], []])
print(result)
```

You should see something like:

```text
[[-2.0, 0.0], [-1.0, -1.0], [0.0, 0.0]]
```

Pairs of (latest, earliest) starts per task - zero difference marks the critical path; big differences mark safe tasks.

## Check yourself

1. What does negative slack mean?
2. How do you use slack of 5 days constructively?
3. Where does all the project's delay risk live?

<details>
<summary>Show answers</summary>

1. The task is already late relative to the promised finish - the deadline needs revisiting or the task needs crashing.

2. Move the task (or its people) by up to 5 days to smooth resource peaks - free flexibility, use it deliberately.

3. On zero-slack tasks - that's where buffer and attention belong.

</details>

## Try this now

Compute slacks for a 5-task network; move the highest-slack task 3 days and prove the finish date didn't move.

---
[← Critical Path Method (CPM)](critical_path_method.md) · [Back to Scheduling library](README.md) · [PERT Expected Duration →](pert_expected_duration.md)
