---
title: "Little's Law Explained: WIP = Throughput x Flow Time"
description: "Simple explanation of Little's Law with bakery and car wash examples. Learn how WIP relates to throughput."
keywords: "Little's law, WIP calculation, throughput, flow time, lean manufacturing, queueing theory"
---

# Little's Law Explained

## The Idea

There is a simple relationship between:
- How much stuff is in progress (WIP)
- How fast you make stuff (throughput)
- How long each takes (flow time)

## The Formula in Python

```python
work_in_progress = throughput_rate * flow_time
```

## Simple Example

Imagine a bakery:

```python
# You bake 10 loaves per hour
# Each loaf takes 4 hours from start to finish

throughput_rate = 10  # loaves per hour
flow_time = 4          # hours per loaf

wip = throughput_rate * flow_time
# = 10 * 4 = 40

print(f'WIP: {wip} loaves in progress')
```

At any moment, there are 40 loaves in various stages of baking.

## Why Does This Work?

Think about it:
- Every hour, 10 new loaves start
- Every hour, 10 finished loaves come out
- Each loaf stays in the bakery for 4 hours
- So at any time, there are 10 * 4 = 40 loaves inside

## Another Example: Car Wash

```python
# Cars enter at 5 per hour
# Each car takes 30 minutes (0.5 hours)

throughput_rate = 5  # cars per hour
flow_time = 0.5       # hours per car

wip = throughput_rate * flow_time
# = 5 * 0.5 = 2.5

print(f'WIP: {wip} cars in the car wash')
```

About 2 to 3 cars are in the car wash at any time.

## Try it with supplycm

```python
from supplycm.lean import wip_calculation

# Factory produces 20 units per hour
# Each unit takes 8 hours

wip = wip_calculation(throughput_rate=20, flow_time=8)
print(f'WIP: {wip} units in progress')
```

## What Can You Do With This?

### Reduce WIP (less stuff in progress)

If you keep throughput the same but reduce flow time:

```python
# Before: 10 per hour, 4 hours each
wip_before = 10 * 4  # = 40

# After: 10 per hour, 2 hours each (improved process)
wip_after = 10 * 2  # = 20

print(f'Before: {wip_before} loaves in progress')
print(f'After: {wip_after} loaves in progress')
print(f'Saved: {wip_before - wip_after} loaves of WIP')
```

### Increase Throughput (make more per hour)

If you keep flow time the same but increase throughput:

```python
# Before: 10 per hour, 4 hours each
throughput_before = 10
wip_before = throughput_before * 4  # = 40

# After: 15 per hour (added capacity)
throughput_after = 15
wip_after = throughput_after * 4  # = 60

print(f'Before: {wip_before} WIP, {throughput_before} per hour')
print(f'After: {wip_after} WIP, {throughput_after} per hour')
```

## The Three Variables

```python
# You can rearrange the formula:

# Original
wip = throughput * flow_time

# Find throughput
throughput = wip / flow_time

# Find flow time
flow_time = wip / throughput
```

## Key Takeaway

Little's Law is simple but powerful:

```python
work_in_progress = throughput_rate * flow_time
```

- More throughput = more WIP
- Longer flow time = more WIP
- To reduce WIP: speed up (less flow time) or slow down (less throughput)
