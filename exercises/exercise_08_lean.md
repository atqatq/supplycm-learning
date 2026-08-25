---
title: "Lean Manufacturing Exercise | OEE and Takt Time"
description: "Practice lean manufacturing: calculate takt time, OEE, and cycle time efficiency."
keywords: "lean exercise, OEE practice, takt time, Little's law, lean manufacturing problems"
---

# Exercise 8: Lean

## Problem

Your production line data:

- Work day: 8 hours = 480 minutes (minus 60 min breaks = 420 min available)
- Customer demand: 210 units per day
- Machine availability: 85%
- Machine performance: 92% of ideal speed
- Quality rate: 97% good parts
- Each unit takes 4 hours total, but only 1 hour is value-added work

### Tasks

1. Calculate takt time
2. Calculate OEE
3. Calculate cycle time efficiency
4. Is your process world-class?

## Your Answer

```
Takt time: ___ minutes/unit
OEE: ___%
Cycle time efficiency: ___%
World-class? ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.lean import takt_time, oee, cycle_time_efficiency

takt = takt_time(420, 210)
oee_value = oee(0.85, 0.92, 0.97)
efficiency = cycle_time_efficiency(1, 4)

print(f"Takt time: {takt} minutes/unit")
print(f"OEE: {oee_value*100:.1f}%")
print(f"Cycle time efficiency: {efficiency*100:.0f}%")
print(f"World-class OEE (85%)? {'Yes' if oee_value >= 0.85 else 'No'}")
```

### Expected Results

1. Takt time = 420 / 210 = 2.0 minutes per unit
2. OEE = 0.85 * 0.92 * 0.97 = 0.758 = 75.8%
3. Cycle time efficiency = 1/4 = 25%
4. OEE is good (75.8%) but not world-class (85%)

</details>
