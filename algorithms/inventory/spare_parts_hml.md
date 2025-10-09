---
title: "Spare Parts: HML Classification | supplycm Algorithm Library"
description: "Plain-English explanation of spare_parts_hml from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, spare_parts_hml, supply chain, plain english, inventory"
---

# Spare Parts: HML Classification

> **Call it:** `from supplycm.inventory import spare_parts_hml` · **Level:** Intermediate · **You need:** basic arithmetic only

HML sorts spares by PRICE: High, Medium, Low. It borrows ABC's value lens for the maintenance store: High-cost parts get purchase approvals and tight custody; Low-cost parts get bins, buckets, and no paperwork theater. Simple, fast, and endlessly useful.

**Think of it like this:** Managing a toolbox: the torque wrench gets a sign-out sheet; the screwdrivers live in a drawer with no questions asked.

## When to reach for it

- Setting approval levels and custody rules by price band
- Fast-triangulating spares control without deep analysis

## Try it with supplycm

```python
from supplycm.inventory import spare_parts_hml

result = spare_parts_hml(prices=[('bearing', 250.0), ('gasket', 15.0), ('motor', 900.0)], high_threshold=100.0, medium_threshold=20.0)
print(result)
```

You should see something like:

```text
[['bearing', 'H'], ['gasket', 'L'], ['motor', 'H']]
```

H/M/L labels come back - the motor and bearing earn tight control; the gasket gets a bin and a reorder card.

## Check yourself

1. What policy follows an H-class part?
2. Why not just use ABC for spares?
3. Can a Low-cost part be Vital?

<details>
<summary>Show answers</summary>

1. Tight custody: approvals for issue, secure storage, careful purchasing - the cost of control is justified.

2. You can - HML is ABC's quick cousin with fixed price cutoffs, made for storerooms without analyst time.

3. Absolutely - that's why HML partners with VED: price decides control level, criticality decides stock policy.

</details>

## Try this now

Band 10 spares into H/M/L with your own cutoffs; pair each H item with its (guessed) VED class and note the surprises.

---
[← Spare Parts: VED Classification](spare_parts_ved.md) · [Back to Inventory library](README.md) · [Spare Parts: SDE Classification →](spare_parts_sde.md)
