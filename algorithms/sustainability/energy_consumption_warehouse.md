---
title: "Warehouse Energy Consumption | supplycm Algorithm Library"
description: "Plain-English explanation of energy_consumption_warehouse from the supplycm Sustainability module, with a runnable Python example and self-check questions."
keywords: "supplycm, sustainability, energy_consumption_warehouse, supply chain, plain english, sustainability"
---

# Warehouse Energy Consumption

> **Call it:** `from supplycm.sustainability import energy_consumption_warehouse` · **Level:** Beginner · **You need:** basic arithmetic only

Multiplies floor area, operating hours, and an energy intensity (kWh per square meter per hour) into a yearly kWh figure. It is the first step of any warehouse energy budget - and the baseline every LED, sensor, or insulation project must beat.

**Think of it like this:** A fitness tracker for your building: it counts what you burn before any diet or workout plan.

## When to reach for it

- Budgeting warehouse electricity for the year
- Setting a before-number to prove savings projects actually worked

## Try it with supplycm

```python
from supplycm.sustainability import energy_consumption_warehouse

result = energy_consumption_warehouse(floor_area=5000, hours_per_day=16, days_per_year=300, kwh_per_sqm_per_hour=0.05)
print(result)
```

You should see something like:

```text
1200000.0
```

1.2 million kWh a year - multiply by your tariff for the money, and use it as the baseline for every efficiency project.

## Check yourself

1. Which two levers cut energy use without touching the building?
2. Cold storage uses 5x the intensity. Why care in slotting?
3. Your LED retrofit claims 20% savings. What proves it?

<details>
<summary>Show answers</summary>

1. Fewer operating hours (lighting/zoning by shift) and lower intensity per square meter (LEDs, sensors).

2. Where and how long you chill goods changes the bill - every sqm of chilled space is expensive air.

3. The same calculation before and after - same area, hours, and intensity factors except the one you changed.

</details>

## Try this now

Compute yearly kWh for 8,000 sqm at 20h/day, 350 days, 0.05 intensity; then recompute at 0.04 after an LED retrofit.

---
[← Carbon Footprint of Transport](carbon_footprint_transport.md) · [Back to Sustainability library](README.md) · [Reverse Logistics Cost →](reverse_logistics_cost.md)

*New to this topic? Start with the core lesson first: [11_sustainability.md](../../modules/11_sustainability.md).*
