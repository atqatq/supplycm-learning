---
title: "Cycle Time Efficiency (PCE) | supplycm Algorithm Library"
description: "Plain-English explanation of cycle_time_efficiency from the supplycm Lean module, with a runnable Python example and self-check questions."
keywords: "supplycm, lean, cycle_time_efficiency, supply chain, plain english, lean"
---

# Cycle Time Efficiency (PCE)

> **Call it:** `from supplycm.lean import cycle_time_efficiency` · **Level:** Intermediate · **You need:** basic arithmetic only

Process cycle efficiency compares the time work is actually being transformed to the total time it waits around. If a part spends 10 days in the process but only 45 minutes being worked on, efficiency is tiny - almost everything is waiting. Lean lives to attack that waiting.

**Think of it like this:** Airport trip: 20 minutes in the air (value) vs 3 hours parking, check-in, security, and baggage (waiting).

## When to reach for it

- Finding improvement targets in order fulfillment or production flow
- Making the case for cutting queues instead of working faster

## Try it with supplycm

```python
from supplycm.lean import cycle_time_efficiency

result = cycle_time_efficiency(value_added_time=0.75, total_cycle_time=240)
print(result)
```

You should see something like:

```text
0.0031
```

Under 1% - the part is touched briefly and then waits for weeks. The biggest lever is queue time, not worker speed.

## Check yourself

1. What are the two ingredients of PCE?
2. Typical PCE in unimproved processes is...?
3. You halve waiting time. What happens to PCE?

<details>
<summary>Show answers</summary>

1. Value-added time (actual transformation) and total cycle time (everything, including all waiting).

2. Often under 5% - most of the time, work is waiting, not being done.

3. Roughly doubles - waiting sits in the denominator, so attacking it lifts efficiency directly.

</details>

## Try this now

An order spends 5 days in process; hands-on work totals 2 hours. Compute PCE and name the top two waits to attack.

---
[← OEE (Overall Equipment Effectiveness)](oee.md) · [Back to Lean library](README.md) · [Little's Law: WIP →](wip_calculation.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
