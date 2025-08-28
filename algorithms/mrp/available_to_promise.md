---
title: "Available-to-Promise (ATP) | supplycm Algorithm Library"
description: "Plain-English explanation of available_to_promise from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, available_to_promise, supply chain, plain english, mrp & production planning"
---

# Available-to-Promise (ATP)

> **Call it:** `from supplycm.mrp import available_to_promise` · **Level:** Intermediate · **You need:** basic arithmetic only

ATP answers the sales question 'if a customer orders TODAY, can I promise it?' - inventory plus arriving receipts minus orders already promised. It stops sales from promising units that operations already gave away, the classic interdepartmental fight.

**Think of it like this:** Concert tickets actually left after all existing reservations - not the venue capacity, the real sellable number.

## When to reach for it

- Inside sales screens before committing delivery dates
- Allocating scarce stock across customers and regions

## Try it with supplycm

```python
from supplycm.mrp import available_to_promise

result = available_to_promise(on_hand=100, scheduled_receipts=[50, 0, 50], customer_orders=[30, 20, 10])
print(result)
```

You should see something like:

```text
[100, 0.0, 40]
```

ATP per period - the first number is what sales may promise for immediate delivery; later periods refill as receipts land.

## Check yourself

1. Why isn't ATP just 'on hand'?
2. ATP goes negative in week 3. Meaning?
3. Who should 'own' ATP numbers?

<details>
<summary>Show answers</summary>

1. Because receipts arrive (good) and orders already promised (bad) both change the real promise-able pool.

2. Over-promised - new orders there need expediting, delay, or a polite no; the number forces the conversation.

3. Operations owns the calculation; sales consumes it - shared visibility beats both sides keeping private math.

</details>

## Try this now

Add receipts of 0 in week 2 and see ATP dip - explain to a salesperson why the big customer can't get a week-2 promise.

---
[← Master Production Schedule (MPS)](master_production_schedule.md) · [Back to MRP & Production Planning library](README.md) · [Capable-to-Promise (CTP) →](capable_to_promise.md)
