---
title: "Line Balancing | supplycm Algorithm Library"
description: "Plain-English explanation of line_balancing from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, line_balancing, supply chain, plain english, scheduling"
---

# Line Balancing

> **Call it:** `from supplycm.scheduling import line_balancing` · **Level:** Advanced · **You need:** basic arithmetic only

Assembly lines are a relay of stations; balance means dividing tasks so every station needs about the same time - the slowest station sets the pace for everyone. This assigns tasks to stations under a target cycle time, respecting precedence.

**Think of it like this:** Rowing an eight: if one rower pulls twice as hard a stroke-load, the boat moves at the slow one's rhythm - balance the load, win the race.

## When to reach for it

- Designing or re-balancing assembly and packing lines
- Chasing takt time with a fixed task set

## Try it with supplycm

```python
from supplycm.scheduling import line_balancing

result = line_balancing(task_times=[3, 5, 2, 4, 1], predecessors=[[], [0], [0], [1], [2, 3]], cycle_time=6)
print(result)
```

You should see something like:

```text
[[0, 2], [1], [3, 4]]
```

Stations as lists of tasks - count stations, check the slowest station's load against the cycle time, and that's your line's heartbeat.

## Check yourself

1. What does cycle time mean on a line?
2. Why does one slow station rule the line?
3. What's the theoretical minimum number of stations?

<details>
<summary>Show answers</summary>

1. The rhythm between consecutive finished units - set by the customer's demand (takt) or by the slowest station.

2. Everything queues behind it - the line's output equals the bottleneck station's output.

3. Total task time divided by cycle time, rounded up - reality needs more when precedence blocks perfect packing.

</details>

## Try this now

Balance the example at cycle time 5; then lower it to 4 and watch the station count grow - narrate the trade-off.

---
[← RPW Priority (Ranked Positional Weight)](rpw_priority.md) · [Back to Scheduling library](README.md) · [LPT (Longest Processing Time) →](lpt_rule.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
