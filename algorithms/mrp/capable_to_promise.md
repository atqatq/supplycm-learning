---
title: "Capable-to-Promise (CTP) | supplycm Algorithm Library"
description: "Plain-English explanation of capable_to_promise from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, capable_to_promise, supply chain, plain english, mrp & production planning"
---

# Capable-to-Promise (CTP)

> **Call it:** `from supplycm.mrp import capable_to_promise` · **Level:** Intermediate · **You need:** basic arithmetic only

CTP goes one step past ATP: not 'what do we have' but 'what could we BUILD' given capacity and lead times. Orders are checked against available production capacity; each order gets a feasible fulfillment date, or -1 when it cannot be done. It is promise-ability for make-to-order business.

**Think of it like this:** A tailor with ATP saying 'fabric on hand' and CTP saying 'and my sewing calendar shows I can finish it by Friday'.

## When to reach for it

- Make/engineer-to-order quoting
- Custom products where inventory cannot answer the question

## Try it with supplycm

```python
from supplycm.mrp import capable_to_promise

result = capable_to_promise(orders=[10, 20, 30], capacities=[50, 50, 50], lead_times=[1, 1, 1])
print(result)
```

You should see something like:

```text
[0, 1, 2]
```

A promised date per order - all feasible here; push orders past capacity and watch dates slip or turn -1.

## Check yourself

1. ATP vs CTP in one line?
2. What makes an order infeasible (-1)?
3. Why is CTP harder to keep accurate than ATP?

<details>
<summary>Show answers</summary>

1. ATP checks stock; CTP checks stock AND the ability to make more in time.

2. Capacity and lead time math cannot land it anywhere within the horizon - quote a later date or add capacity.

3. It needs live capacity data from the shop floor - stale routings or calendars quietly poison every promise.

</details>

## Try this now

Overload period 1 with orders beyond capacity 50 and trace how the promised dates shift to later periods.

---
[← Available-to-Promise (ATP)](available_to_promise.md) · [Back to MRP & Production Planning library](README.md) · [Lot-for-Lot (L4L) →](lot_size_rule_l4l.md)
