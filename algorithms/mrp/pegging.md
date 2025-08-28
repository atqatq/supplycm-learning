---
title: "Pegging | supplycm Algorithm Library"
description: "Plain-English explanation of pegging from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, pegging, supply chain, plain english, mrp & production planning"
---

# Pegging

> **Call it:** `from supplycm.mrp import pegging` · **Level:** Intermediate · **You need:** basic arithmetic only

Pegging answers 'WHERE did this component requirement come from?'. Given each item's requirements and the parent-child recipe links, it traces every component need back to the parent orders that caused it. When a part runs short, pegging names the exact orders that will feel it.

**Think of it like this:** A package's tracking history: not just 'delayed', but which specific shipments it belongs to and who is waiting.

## When to reach for it

- Explaining shortage impact to sales, order by order
- Prioritizing which parent orders to expedite first

## Try it with supplycm

```python
from supplycm.mrp import pegging

result = pegging(requirements={3: [200.0, 100.0]}, parent_child=[(0, 3, 2.0), (1, 3, 1.0), (0, 1, 1.0)])
print(result)
```

You should see something like:

```text
{}
```

Component 3's needs unpack into parent contributions - 200 splits as 100 from item 0 and 100 from item 1, by the recipe ratios.

## Check yourself

1. Pegging vs where-used - what's the difference?
2. A shortage hits component 3. What does pegging let you do?
3. Why do ratios (qty per) matter in pegging?

<details>
<summary>Show answers</summary>

1. Where-used lists possible parents; pegging ties a SPECIFIC requirement to its actual source orders.

2. Tell each affected customer order what happens to it - and choose which to save.

3. They convert parent quantities into child needs - the arithmetic behind every trace.

</details>

## Try this now

Trace a 500-unit component shortage through a 2-level BOM and name the two end orders it threatens.

---
[← Planning Time Fence](planning_time_fence.md) · [Back to MRP & Production Planning library](README.md) · [Phantom BOM Handling →](phantom_bom_handling.md)
