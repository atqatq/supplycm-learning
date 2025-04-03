---
title: "Little's Law: WIP | supplycm Algorithm Library"
description: "Plain-English explanation of wip_calculation from the supplycm Lean module, with a runnable Python example and self-check questions."
keywords: "supplycm, lean, wip_calculation, supply chain, plain english, lean"
---

# Little's Law: WIP

> **Call it:** `from supplycm.lean import wip_calculation` · **Level:** Beginner · **You need:** basic arithmetic only

Little's Law links three things you already know: WIP (work in progress) = throughput rate x flow time. If 10 orders finish per hour and each order spends 3 hours in the system, you have about 30 orders in progress. It is supply chain arithmetic at its most useful.

**Think of it like this:** A highway: cars entering per minute times minutes on the road equals cars on the road at any moment.

## When to reach for it

- Checking how much inventory a process speed implies
- Diagnosing queues: if WIP is way above the math, flow is blocked

## Try it with supplycm

```python
from supplycm.lean import wip_calculation

result = wip_calculation(throughput_rate=10, flow_time=3)
print(result)
```

You should see something like:

```text
30
```

30 units in progress on average - cut flow time to 2 hours and WIP falls to 20 without touching output.

> **Watch out:** Little's Law is pure arithmetic - but always check the units (per hour vs per day) before multiplying.

## Check yourself

1. Throughput 20/hour, flow time 30 minutes. WIP?
2. You want less WIP without slowing throughput. Which lever?
3. Why is high WIP a problem if output is fine?

<details>
<summary>Show answers</summary>

1. 10 - convert units first: 0.5 hour x 20/hour = 10 units.

2. Flow time - shorten queues and waits.

3. Cash sits on the floor, defects hide longer, and lead times stretch - WIP is the smell of blocked flow.

</details>

## Try this now

A clinic serves 4 patients/hour; each spends 45 minutes inside. How many patients are 'in the system' on average?

---
[← Cycle Time Efficiency (PCE)](cycle_time_efficiency.md) · [Back to Lean library](README.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
