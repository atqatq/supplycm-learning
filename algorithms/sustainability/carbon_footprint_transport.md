---
title: "Carbon Footprint of Transport | supplycm Algorithm Library"
description: "Plain-English explanation of carbon_footprint_transport from the supplycm Sustainability module, with a runnable Python example and self-check questions."
keywords: "supplycm, sustainability, carbon_footprint_transport, supply chain, plain english, sustainability"
---

# Carbon Footprint of Transport

> **Call it:** `from supplycm.sustainability import carbon_footprint_transport` · **Level:** Beginner · **You need:** basic arithmetic only

This estimates CO2 released to move goods: distance x weight x an emission factor that depends on the mode (truck, ship, plane). The output makes logistics choices carbon-visible: air freight can dwarf sea freight for the same load.

**Think of it like this:** A calorie counter, but for shipments: every kilometer and kilogram adds to the meal's total.

## When to reach for it

- Comparing transport modes or routes on emissions
- Reporting supply chain emissions for sustainability targets

## Try it with supplycm

```python
from supplycm.sustainability import carbon_footprint_transport

result = carbon_footprint_transport(distance=2000, weight=500, emission_factor=0.062)
print(result)
```

You should see something like:

```text
62000.0
```

6,200 kg of CO2 for this lane - now run the same load by rail or sea and see the drop for yourself.

## Check yourself

1. What does the emission factor represent?
2. Same truck, twice the distance: how does CO2 change?
3. Air freight emits ~20x sea. Why do firms still fly cargo?

<details>
<summary>Show answers</summary>

1. CO2 per tonne-kilometer for the mode - trucks pollute more per km than ships or rail.

2. Doubles - the relationship is linear in distance and weight.

3. Speed: launches, stockouts, and perishables buy the premium - the job is knowing when it is worth it.

</details>

## Try this now

Compare CO2 for 1 tonne over 3,000 km by truck (0.062) vs sea (0.010); then argue one case where flying is justified.

---
[Back to Sustainability library](README.md) · [Warehouse Energy Consumption →](energy_consumption_warehouse.md)

*New to this topic? Start with the core lesson first: [11_sustainability.md](../../modules/11_sustainability.md).*
