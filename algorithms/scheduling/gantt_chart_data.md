---
title: "Gantt Chart Data | supplycm Algorithm Library"
description: "Plain-English explanation of gantt_chart_data from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, gantt_chart_data, supply chain, plain english, scheduling"
---

# Gantt Chart Data

> **Call it:** `from supplycm.scheduling import gantt_chart_data` · **Level:** Beginner · **You need:** basic arithmetic only

Turns a schedule of (machine, start, end) triples into per-machine rows ready for a Gantt chart - the horizontal bars every scheduler's wall demands. Numbers to picture, in one call. Communication is half of scheduling.

**Think of it like this:** Turning a train timetable into the station's actual display: same data, now human-readable at a glance.

## When to reach for it

- Feeding visualization tools or wall printouts
- Sanity-checking schedules visually before release

## Try it with supplycm

```python
from supplycm.scheduling import gantt_chart_data

result = gantt_chart_data(schedule={(0, 0): (0, 3), (1, 0): (0, 4), (0, 1): (4, 6)}, num_machines=2)
print(result)
```

You should see something like:

```text
[[[0, 0, 3], [1, 0, 4]], [[0, 4, 6]]]
```

Rows per machine, each with (job, start, end) - draw them as bars and the schedule's gaps and overlaps become obvious.

## Check yourself

1. What does a gap between bars on one machine mean?
2. Why visualize before executing schedules?
3. What belongs on the horizontal axis?

<details>
<summary>Show answers</summary>

1. Idle time - capacity nobody used; sometimes inevitable, sometimes the improvement target.

2. Eyes catch overlaps, starvation, and absurdities that numbers hide - one glance beats one spreadsheet.

3. Time - bars span start to end per operation; length is duration, position is the promise.

</details>

## Try this now

Chart the example by hand on grid paper; circle the idle gaps and name the job that caused each.

---
[← Two-Machine Open Shop](two_machine_open_shop.md) · [Back to Scheduling library](README.md) · [Earliest Start Schedule →](earliest_start_schedule.md)
