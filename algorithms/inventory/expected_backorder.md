---
title: "Expected Backorder Units | supplycm Algorithm Library"
description: "Plain-English explanation of expected_backorder from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, expected_backorder, supply chain, plain english, inventory"
---

# Expected Backorder Units

> **Call it:** `from supplycm.inventory import expected_backorder` · **Level:** Advanced · **You need:** basic arithmetic only

Even with safety stock, some cycles end short. This computes the EXPECTED number of units on backorder at a random moment - the average 'we owe you' sitting in the system. It feeds fill-rate math and honest service conversations.

**Think of it like this:** A restaurant's average waitlist length: not how often you're full, but how many parties are typically standing at the door.

## When to reach for it

- Quantifying the ongoing backorder burden of a policy
- Input to total cost: backorder units x cost per unit-year

## Try it with supplycm

```python
from supplycm.inventory import expected_backorder

result = expected_backorder(safety_stock=20, demand_std=15, lead_time=3)
print(result)
```

You should see something like:

```text
3.2928
```

A small expected backlog - on average only a fraction of a unit waits; raise demand_std to 30 and watch it grow fast.

## Check yourself

1. Expected backorder 0.4 units - is that good?
2. How does this differ from stockout FREQUENCY?
3. What tames expected backorders fastest?

<details>
<summary>Show answers</summary>

1. Context decides: 0.4 across a key B2B item may be a crisis; across a low-value commodity, fine.

2. Frequency counts cycles that go short; expected backorder counts UNITS short, weighted by how deep.

3. More safety stock - but variability reduction (better forecasts, reliable suppliers) works without holding cost.

</details>

## Try this now

Compute expected backorders at safety stock 0, 20, 40 and sketch the diminishing-returns curve you see.

---
[← Fill Rate Calculation](fill_rate_calculation.md) · [Back to Inventory library](README.md) · [Expected On-Hand Inventory →](expected_on_hand.md)
