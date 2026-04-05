# Module 8: Working Smart (Lean)

## The Big Idea

Lean means doing more with less. It is about removing waste and making things flow smoothly.

## Why Does It Matter?

Waste costs money. Every wasted minute, every wasted material, every wasted movement adds up. Lean helps you find and remove waste.

## The 8 Wastes (DOWNTIME)

Lean identifies 8 types of waste. Remember them with DOWNTIME:

1. **D**efects: Products that are wrong and need fixing
2. **O**verproduction: Making more than needed
3. **W**aiting: Time spent waiting for the next step
4. **N**on-utilized talent: Not using people's skills
5. **T**ransportation: Moving stuff unnecessarily
6. **I**nventory: Keeping too much stock
7. **M**otion: People moving more than needed
8. **E**xcess processing: Doing more work than the customer wants

## Takt Time: The Pace of Demand

Takt time is the rhythm at which you need to produce to meet customer demand.

### The Formula in Python Notation

```python
takt_time = available_time / customer_demand
```

### Example

If you have 480 minutes available and customers want 240 units per day:

```python
available_time = 480
customer_demand = 240
takt_time = available_time / customer_demand
# takt_time = 2.0 minutes per unit
```

You need to produce one unit every 2 minutes.

### Try it with supplycm

```python
from supplycm.lean import takt_time

takt = takt_time(available_time=480, customer_demand=240)
print(f"Takt time: {takt} minutes per unit")
```

## OEE: Overall Equipment Effectiveness

OEE measures how well your equipment is used. It combines three things:

1. **Availability**: How much time the machine is running
2. **Performance**: How fast it runs compared to ideal
3. **Quality**: How many good products it makes

### The Formula in Python Notation

```python
oee = availability * performance * quality
```

### Example

```python
availability = 0.85   # running 85% of scheduled time
performance = 0.90   # running at 90% of max speed
quality = 0.95        # 95% of products are good

oee = availability * performance * quality
# oee = 0.727 = 72.7%
```

### Try it with supplycm

```python
from supplycm.lean import oee

result = oee(availability=0.85, performance=0.90, quality=0.95)
print(f"OEE: {result*100:.1f}%")
```

**World class OEE is 85%.** Most companies are around 60%.

## Little's Law: WIP = Throughput x Flow Time

Little's Law is a simple but powerful relationship:

### The Formula in Python Notation

```python
work_in_progress = throughput_rate * flow_time
```

### Example

If you produce 10 units per hour and each takes 5 hours to make:

```python
throughput_rate = 10  # units per hour
flow_time = 5          # hours per unit

wip = throughput_rate * flow_time
# wip = 50 units in progress
```

### Try it with supplycm

```python
from supplycm.lean import wip_calculation

wip = wip_calculation(throughput_rate=10, flow_time=5)
print(f"WIP: {wip} units")
```

## Cycle Time Efficiency

Cycle time efficiency measures how much of your total time is actually adding value.

### The Formula in Python Notation

```python
efficiency = value_added_time / total_cycle_time
```

### Example

If a product takes 50 hours from start to finish, but only 5 hours of that is actual work:

```python
value_added_time = 5
total_cycle_time = 50

efficiency = value_added_time / total_cycle_time
# efficiency = 0.10 = 10%
```

Most processes are less than 10% efficient. There is a lot of room for improvement.

### Try it with supplycm

```python
from supplycm.lean import cycle_time_efficiency

efficiency = cycle_time_efficiency(value_added_time=5, total_cycle_time=50)
print(f"Efficiency: {efficiency*100:.0f}%")
```

## The 5S Method

5S is a method to organize your workspace:

1. **S**ort: Remove what you do not need
2. **S**et in order: Give everything a place
3. **S**hine: Clean everything
4. **S**tandardize: Make rules for how things should be
5. **S**ustain: Keep it going

## Quick Quiz

1. What does DOWNTIME stand for?
2. If `available_time = 360` and `customer_demand = 180`, what is `takt_time`?
3. What is the formula for OEE?
4. What does Little's Law say?
5. What are the 5 S's?

<details>
<summary>Click to reveal answers</summary>

1. Defects, Overproduction, Waiting, Non-utilized talent, Transportation, Inventory, Motion, Excess processing
2. `takt_time = 360 / 180` = 2 minutes per unit
3. `oee = availability * performance * quality`
4. `work_in_progress = throughput_rate * flow_time`
5. Sort, Set in order, Shine, Standardize, Sustain

</details>

## Exercise

You run a small factory.

1. `available_time = 420` minutes (7 hours)
2. `customer_demand = 140` products per day
3. `availability = 0.80`
4. `performance = 0.90`
5. `quality = 0.95`
6. Each product takes 3 hours to make, but only 30 minutes is actual work

Calculate:
- Takt time
- OEE
- WIP (if you produce at the throughput rate)
- Cycle time efficiency

## Key Words

- **Lean**: Doing more with less by removing waste
- **Waste**: Anything that does not add value (DOWNTIME)
- **Takt time**: The pace of customer demand
- **OEE**: Overall Equipment Effectiveness
- **Little's Law**: WIP = Throughput x Flow Time
- **5S**: A method to organize workspace

## What's Next?

Now you know how to work efficiently. But how do you plan what to make? The next lesson is about S&OP.

Next: [Module 9 - Planning Ahead (S&OP)](09_planning.md)
