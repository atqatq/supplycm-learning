# Module 11: Being Green (Sustainability)

## The Big Idea

Sustainability means meeting today's needs without hurting future generations. In supply chains, this means reducing environmental impact.

## Why Does It Matter?

- Customers prefer green companies
- Laws require lower emissions
- Reducing waste often saves money
- It is the right thing to do

## Carbon Footprint

Your carbon footprint is how much CO2 your operations produce. Transportation is a big contributor.

### The Formula in Python Notation

```python
co2_emissions = distance * weight * emission_factor
```

Where:
- `distance` = how far the truck travels (km)
- `weight` = how heavy the load is (tonnes)
- `emission_factor` = CO2 per tonne-km (depends on transport mode)

### Try it with supplycm

```python
from supplycm.sustainability import carbon_footprint_transport

distance = 500   # km
weight = 10      # tonnes

co2 = carbon_footprint_transport(distance, weight)
print(f"CO2 emissions: {co2} kg")
```

### Emission Factors (approximate)

| Transport | kg CO2 per tonne-km |
|-----------|---------------------|
| Truck | 0.062 |
| Train | 0.022 |
| Ship | 0.016 |
| Air | 0.602 |

Air transport produces about 10 times more CO2 than truck, and 37 times more than ship.

## Reverse Logistics

Traditional logistics moves products forward: factory to customer.

Reverse logistics moves products backward: customer back to factory.

### Why reverse logistics matters:

1. **Returns**: Customers return products
2. **Recycling**: Materials can be reused
3. **Repairs**: Products can be fixed
4. **Disposal**: Safe disposal of hazardous items

### Try it with supplycm

```python
from supplycm.sustainability import reverse_logistics_cost

return_rate = 0.10       # 10% of products returned
unit_cost = 100          # original cost
processing_cost = 5      # cost to process each return
disposal_cost = 2        # cost to dispose
resale_value = 30        # revenue from reselling

cost = reverse_logistics_cost(return_rate, unit_cost, processing_cost,
                               disposal_cost, resale_value)
print(f"Net cost per unit sold: ${cost:.2f}")
```

## Energy Consumption

Warehouses use a lot of energy for lighting, heating, and cooling.

### Try it with supplycm

```python
from supplycm.sustainability import energy_consumption_warehouse

floor_area = 10000    # square meters
hours_per_day = 24
days_per_year = 365

energy = energy_consumption_warehouse(floor_area, hours_per_day, days_per_year)
print(f"Annual energy: {energy} kWh")
```

## How to Reduce Environmental Impact

### 1. Optimize Routes
Less driving = less fuel = less CO2. Use the routing algorithms from Module 6.

### 2. Use Green Transport
- Ship instead of air when possible
- Use electric trucks for local delivery
- Combine shipments to reduce trips

### 3. Reduce Packaging
- Use recyclable materials
- Right-size packages (no big boxes for small items)
- Reuse packaging when possible

### 4. Energy Efficiency
- LED lighting in warehouses
- Better insulation
- Solar panels on warehouse roofs

### 5. Local Sourcing
Buy from nearby suppliers to reduce transport distance.

## The Three R's

1. **Reduce**: Use less in the first place
2. **Reuse**: Use things multiple times
3. **Recycle**: Turn old things into new things

## Quick Quiz

1. What is the formula for transport carbon footprint?
2. Which transport mode produces the most CO2 per tonne-km?
3. What is reverse logistics?
4. What are the three R's of sustainability?

<details>
<summary>Click to reveal answers</summary>

1. `co2_emissions = distance * weight * emission_factor`
2. Air transport (about 0.6 kg CO2 per tonne-km)
3. Moving products from customer back to supplier (returns, recycling, repairs)
4. Reduce, Reuse, Recycle

</details>

## Exercise

You ship 1000 packages per week. Each package travels 200 km by truck and weighs 5 kg.

1. Calculate weekly CO2 emissions
2. If you switch to train (same route), how much CO2 do you save?
3. What if you source locally and reduce distance to 50 km?

## Key Words

- **Sustainability**: Meeting today's needs without hurting the future
- **Carbon footprint**: Amount of CO2 produced
- **Reverse logistics**: Moving products backward (returns, recycling)
- **Emission factor**: CO2 per unit of transport
- **Three R's**: Reduce, Reuse, Recycle

## What's Next?

You have learned all the pieces. The final module puts everything together.

Next: [Module 12 - Putting It All Together](12_putting_it_together.md)
