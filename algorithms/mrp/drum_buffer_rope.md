---
title: "Drum-Buffer-Rope (DBR) | supplycm Algorithm Library"
description: "Plain-English explanation of drum_buffer_rope from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, drum_buffer_rope, supply chain, plain english, mrp & production planning"
---

# Drum-Buffer-Rope (DBR)

> **Call it:** `from supplycm.mrp import drum_buffer_rope` · **Level:** Advanced · **You need:** basic arithmetic only

Theory of Constraints in one schedule: the bottleneck (drum) sets the pace for everything; a time buffer protects it from starvation; the rope links release of new work to the drum's actual capacity. This schedules production limited by the constraint instead of wishful demand.

**Think of it like this:** A highway tunnel sets the flow for the whole road - cars enter at tunnel pace (rope), and a safety gap (buffer) keeps the tunnel from running empty.

## When to reach for it

- Any system with a clear bottleneck (almost all real ones)
- Replacing 'keep everyone busy' logic with 'keep the bottleneck busy'

## Try it with supplycm

```python
from supplycm.mrp import drum_buffer_rope

result = drum_buffer_rope(demands=[10, 20, 30], constraint_capacity=25, buffer_time=2)
print(result)
```

You should see something like:

```text
[30, 0.0, 0.0]
```

A paced schedule capped by the constraint - some demand waits by design; protecting the drum beats flooding it.

## Check yourself

1. What do the drum, buffer, and rope each represent?
2. Non-bottleneck machines idle sometimes. Waste?
3. The bottleneck gets faster. What must change?

<details>
<summary>Show answers</summary>

1. Drum: the constraint's pace; buffer: protection time/stock before it; rope: release tied to that pace.

2. Not really - their idle time is the price of keeping the constraint fed and on schedule.

3. The whole system's pace - the drum beats differently, so buffers and release rates are re-tuned.

</details>

## Try this now

Raise capacity from 25 to 35 on the example and describe what happens to total throughput and waiting.

---
[← Rough-Cut Capacity Planning (RCCP)](rough_cut_capacity_planning.md) · [Back to MRP & Production Planning library](README.md) · [Kanban Card Sizing →](kaban_sizing.md)
