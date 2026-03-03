---
title: "Center of Gravity Location | supplycm Algorithm Library"
description: "Plain-English explanation of center_of_gravity from the supplycm Network Design module, with a runnable Python example and self-check questions."
keywords: "supplycm, network_design, center_of_gravity, supply chain, plain english, network design"
---

# Center of Gravity Location

> **Call it:** `from supplycm.network_design import center_of_gravity` · **Level:** Beginner · **You need:** basic arithmetic only

Where should the warehouse go? The center of gravity weights every customer's location by demand volume and returns the balance point - the spot that minimizes total straight-line shipping effort. Not the final answer, but the perfect first draft.

**Think of it like this:** Balancing a tray of plates: put your finger where the weight centers - heavy plates pull the balance point toward them.

## When to reach for it

- First-pass warehouse or DC siting
- Sanity-checking candidate locations against demand geography

## Try it with supplycm

```python
from supplycm.network_design import center_of_gravity

result = center_of_gravity(customers=[(10, 20, 100), (30, 40, 50), (15, 35, 200)])
print(result)
```

You should see something like:

```text
[15.7143, 31.4286]
```

A coordinate pair - the demand-weighted balance point; map your candidates against it and ask why yours differs.

## Check yourself

1. Why weight by demand volume?
2. What does the method ignore that reality adds?
3. How do you use it without over-trusting it?

<details>
<summary>Show answers</summary>

1. Because shipping 10 truckloads matters 10x more than one - volume turns geography into economics.

2. Roads, land costs, labor, and borders - it computes a physics answer, not a zoning-approved one.

3. Shortlist real sites near the point, then score THEM on total costs - the center generates candidates, not decisions.

</details>

## Try this now

Find the center for 4 invented customers, then deliberately move the heaviest customer and watch the point chase it.

---
[← Break-Even Analysis](break_even_analysis.md) · [Back to Network Design library](README.md) · [Facility Location (Fixed Cost) →](facility_location_fixed_cost.md)
