---
title: "Spare Parts: SDE Classification | supplycm Algorithm Library"
description: "Plain-English explanation of spare_parts_sde from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, spare_parts_sde, supply chain, plain english, inventory"
---

# Spare Parts: SDE Classification

> **Call it:** `from supplycm.inventory import spare_parts_sde` · **Level:** Advanced · **You need:** basic arithmetic only

SDE classifies by ACQUISITION DIFFICULTY: Scarce (imported, sole-source, months of lead time), Difficult (multi-week, few suppliers), Easy (buy anytime). Difficulty - not price or movement - decides how aggressively you hedge. Scarcity is the silent budget killer in maintenance.

**Think of it like this:** Road-trip planning: fuel is Easy (buy anywhere), a specific tire for a 1998 import is Scarce - you carry the spare BEFORE the trip, not during.

## When to reach for it

- Deciding safety stock for long-lead, sole-source spares
- Explaining why a cheap part deserves expensive attention

## Try it with supplycm

```python
from supplycm.inventory import spare_parts_sde

result = spare_parts_sde(lead_time_data=[('imported-bearing', 120.0), ('standard-seal', 20.0), ('custom-gear', 45.0)], scarce_threshold=90, difficult_threshold=30)
print(result)
```

You should see something like:

```text
[['imported-bearing', 'S'], ['standard-seal', 'E'], ['custom-gear', 'D']]
```

S/D/E labels: the 120-day import is Scarce and earns a deliberate buffer; the 20-day seal is Easy and earns none.

## Check yourself

1. Why does lead time dominate spares policy?
2. A Scarce part is also cheap. Stock it?
3. How do you de-scarify a part?

<details>
<summary>Show answers</summary>

1. Because downtime cost accrues DAILY while you wait - a 120-day hole in availability is a production risk, not a procurement detail.

2. Almost certainly - scarcity, not price, drives the exposure; cheap insurance with huge downside protection.

3. Qualify second sources, standardize across machines, or negotiate vendor-held consignment - attack the difficulty itself.

</details>

## Try this now

Classify 6 spares by lead time; for each Scarce item, write the one mitigation that would move it toward D or E.

---
[← Spare Parts: HML Classification](spare_parts_hml.md) · [Back to Inventory library](README.md)
