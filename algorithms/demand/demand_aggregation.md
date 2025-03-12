---
title: "Demand Aggregation | supplycm Algorithm Library"
description: "Plain-English explanation of demand_aggregation from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, demand_aggregation, supply chain, plain english, demand planning"
---

# Demand Aggregation

> **Call it:** `from supplycm.demand import demand_aggregation` · **Level:** Beginner · **You need:** basic arithmetic only

Aggregation rolls daily demand up into bigger buckets - weekly, monthly, or quarterly. Planners work at the level where decisions happen: buyers order weekly, finance plans monthly. One call converts a jumpy daily history into the calendar your process actually uses.

**Think of it like this:** Like turning 365 daily diary pages into 12 monthly summaries - same story, readable at a glance.

## When to reach for it

- Converting daily POS data into the weekly buckets your S&OP uses
- Reducing noise before forecasting - aggregated demand is calmer

## Try it with supplycm

```python
from supplycm.demand import demand_aggregation

result = demand_aggregation([5, 3, 4, 2, 6, 1, 5, 4, 4, 3, 2, 5, 6, 4], bucket_size=7)
print(result)
```

You should see something like:

```text
[26, 28]
```

Each output value is one week's total - 14 noisy days become 2 calm weekly numbers that are far easier to forecast.

> **Watch out:** Match your aggregation bucket to the real decision cadence - weekly buyer, monthly S&OP.

## Check yourself

1. Why does aggregated demand forecast better than daily demand?
2. Give one thing you LOSE when you aggregate.
3. Your supplier orders monthly but your data is daily. What do you do?

<details>
<summary>Show answers</summary>

1. Buckets average out daily randomness - noise cancels, so patterns stand out more.

2. Timing detail within the bucket - daily spikes and hour-of-day patterns vanish.

3. Aggregate to monthly buckets so your forecast matches the decision rhythm.

</details>

## Try this now

Aggregate 28 invented daily values into weeks, then eyeball: which weeks were strong and why?

---
[Back to Demand Planning library](README.md) · [Demand Disaggregation →](demand_disaggregation.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
