# OEE Breakdown

## What is OEE?

OEE stands for Overall Equipment Effectiveness. It tells you how well your equipment is used.

## The Formula in Python

```python
oee = availability * performance * quality
```

## The Three Parts

### Part 1: Availability

Are you running when you should be?

```python
# Example: Machine scheduled for 8 hours (480 min)
# But it was down for 72 minutes (breakdowns, setup)

scheduled_time = 480
downtime = 72
run_time = scheduled_time - downtime
# = 480 - 72 = 408 minutes

availability = run_time / scheduled_time
# = 408 / 480 = 0.85 = 85%

print(f'Availability: {availability * 100:.0f}%')
```

### Part 2: Performance

Are you running at full speed?

```python
# Example: Machine should make 10 units per minute
# It actually made 3,672 units in 408 minutes

ideal_speed = 10  # units per minute
actual_units = 3672
run_time = 408

ideal_time = actual_units / ideal_speed
# = 3672 / 10 = 367.2 minutes needed at full speed

performance = ideal_time / run_time
# = 367.2 / 408 = 0.90 = 90%

print(f'Performance: {performance * 100:.0f}%')
```

### Part 3: Quality

Are the products good?

```python
# Example: Made 3672 units, but 73 were bad

total_units = 3672
bad_units = 73
good_units = total_units - bad_units
# = 3672 - 73 = 3599

quality = good_units / total_units
# = 3599 / 3672 = 0.98 = 98%

print(f'Quality: {quality * 100:.0f}%')
```

## Putting It All Together

```python
availability = 0.85
performance = 0.90
quality = 0.98

oee = availability * performance * quality
# = 0.85 * 0.90 * 0.98
# = 0.7497
# = 75%

print(f'OEE: {oee * 100:.1f}%')
```

### Try it with supplycm

```python
from supplycm.lean import oee

result = oee(0.85, 0.90, 0.98)
print(f'OEE: {result * 100:.1f}%')
```

## What Each Part Tells You

### Low Availability?
Your machine is down too much. Fix:
- Preventive maintenance
- Faster setup
- Reduce breakdowns

### Low Performance?
Your machine is running slow. Fix:
- Check for wear
- Train operators
- Remove small stops

### Low Quality?
Too many bad products. Fix:
- Better materials
- Better process
- Quality checks

## World Class Benchmarks

| Metric | World Class | Typical |
|--------|-------------|---------|
| Availability | 90% | 60-70% |
| Performance | 95% | 70-80% |
| Quality | 99% | 90-95% |
| OEE | 85% | 50-60% |

## Key Takeaway

```python
oee = availability * performance * quality
```

- Availability: Are you running?
- Performance: Are you fast?
- Quality: Are you good?
- OEE: All three combined
