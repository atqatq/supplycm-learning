---
title: "OEE (Overall Equipment Effectiveness) | supplycm Algorithm Library"
description: "Plain-English explanation of oee from the supplycm Lean module, with a runnable Python example and self-check questions."
keywords: "supplycm, lean, oee, supply chain, plain english, lean"
---

# OEE (Overall Equipment Effectiveness)

> **Call it:** `from supplycm.lean import oee` · **Level:** Beginner · **You need:** basic arithmetic only

OEE multiplies three questions: Was the machine running when needed (availability)? Did it run at full speed (performance)? Was the output good (quality)? Multiply the three percentages to get one 0-100% effectiveness score. World class is around 85%.

**Think of it like this:** A player's season rating: games played x minutes per game x points per minute - all three matter.

## When to reach for it

- Diagnosing why a machine's real output falls short of its paper capacity
- Prioritizing improvement: which factor (downtime? speed? defects?) drags most?

## Try it with supplycm

```python
from supplycm.lean import oee

result = oee(availability=0.9, performance=0.8, quality=0.99)
print(result)
```

You should see something like:

```text
0.7128
```

About 71% - decent, but the gap to 85% shows there is real money hidden in speed losses and stoppages.

## Check yourself

1. A = 90%, P = 90%, Q = 90%. Is OEE 90%?
2. Which OEE factor do minor stops and slow cycling hit?
3. Why is OEE better than just 'uptime'?

<details>
<summary>Show answers</summary>

1. No - multiply them: 0.9 x 0.9 x 0.9 = about 73%. Three 'good' numbers hide a big overall loss.

2. Performance - the machine runs but slower than ideal.

3. Uptime ignores speed and quality - a machine can be 'up', running slowly, making scrap, and uptime still says 100%.

</details>

## Try this now

Compute OEE for A=0.85, P=0.95, Q=0.99, then for A=0.95, P=0.95, Q=0.85 - which improvement matters more here?

---
[← Takt Time](takt_time.md) · [Back to Lean library](README.md) · [Cycle Time Efficiency (PCE) →](cycle_time_efficiency.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
