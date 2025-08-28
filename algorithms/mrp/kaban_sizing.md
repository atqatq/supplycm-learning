---
title: "Kanban Card Sizing | supplycm Algorithm Library"
description: "Plain-English explanation of kaban_sizing from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, kaban_sizing, supply chain, plain english, mrp & production planning"
---

# Kanban Card Sizing

> **Call it:** `from supplycm.mrp import kaban_sizing` · **Level:** Intermediate · **You need:** basic arithmetic only

Kanban controls work-in-progress with cards: each card authorizes one container. This computes how many cards you need from demand rate, replenishment lead time, container size, and a safety factor. Too few cards starve the line; too many quietly rebuild the warehouse.

**Think of it like this:** Restaurant plates: the kitchen cooks when empty plates return - the number of plates in circulation controls how much food exists at once.

## When to reach for it

- Setting up pull systems on repetitive production
- Tuning WIP after demand or lead time changes

## Try it with supplycm

```python
from supplycm.mrp import kaban_sizing

result = kaban_sizing(demand_rate=100, lead_time=2, container_size=50, safety_factor=1.1)
print(result)
```

You should see something like:

```text
5
```

About 5 cards - five containers in circulation cover demand during replenishment plus a 10% cushion.

## Check yourself

1. What does each kanban card authorize?
2. Demand doubles. What happens to card count?
3. Why multiply by a safety factor?

<details>
<summary>Show answers</summary>

1. One container of parts - total cards x container size is your WIP ceiling.

2. It roughly doubles - recompute, or the line starves between replenishments.

3. Real lead times wobble - the factor absorbs ordinary variability without a stockout every week.

</details>

## Try this now

Size cards for demand 200/day, lead time 0.5 day, containers of 25 with 20% safety - then explain each number's role.

---
[← Drum-Buffer-Rope (DBR)](drum_buffer_rope.md) · [Back to MRP & Production Planning library](README.md)

*New to this topic? Start with the core lesson first: [08_lean.md](../../modules/08_lean.md).*
