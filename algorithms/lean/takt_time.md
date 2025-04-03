---
title: "Takt Time | supplycm Algorithm Library"
description: "Plain-English explanation of takt_time from the supplycm Lean module, with a runnable Python example and self-check questions."
keywords: "supplycm, lean, takt_time, supply chain, plain english, lean"
---

# Takt Time

> **Call it:** `from supplycm.lean import takt_time` · **Level:** Beginner · **You need:** basic arithmetic only

Takt time is the heartbeat your production must match: available work time divided by what the customer actually ordered. If customers need 80 units in an 8-hour day, takt is one unit every 6 minutes. Produce slower and you disappoint; faster and you build waste.

**Think of it like this:** Rowing to a drumbeat: the drummer (customer demand) sets the pace, everyone strokes to it.

## When to reach for it

- Line design: how fast must each station complete its work?
- Daily management: comparing actual output rhythm to customer pull

## Try it with supplycm

```python
from supplycm.lean import takt_time

result = takt_time(available_time=480, customer_demand=80)
print(result)
```

You should see something like:

```text
6.0
```

6.0 - one finished unit must leave the line every 6 minutes to satisfy demand without overproduction.

## Check yourself

1. Customer demand doubles but hours stay fixed. What happens to takt?
2. Produce faster than takt - is that good?
3. Where does 'takt' come from?

<details>
<summary>Show answers</summary>

1. It halves - the line must beat twice as fast, or you add capacity/time.

2. No - it builds inventory nobody ordered (the worst lean waste).

3. The German word for baton/metronome - the conductor's beat for the whole orchestra.

</details>

## Try this now

A bakery works 7 hours (420 minutes) and must deliver 140 breads. Compute takt and check which tasks fit within it.

---
[Back to Lean library](README.md) · [OEE (Overall Equipment Effectiveness) →](oee.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
