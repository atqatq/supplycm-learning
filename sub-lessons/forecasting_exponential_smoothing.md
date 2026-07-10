# Understanding Exponential Smoothing

## The Idea

Recent data matters more than old data. Exponential smoothing gives more weight to recent days.

## The Formula in Python

```python
forecast_today = alpha * sales_yesterday + (1 - alpha) * forecast_yesterday
```

Where:
- `alpha` is a number between 0 and 1
- Higher alpha = care more about recent data
- Lower alpha = care more about history

## Step by Step Example

Let us say your sales are: [100, 110, 105, 120]

And alpha = 0.3 (30% weight on recent, 70% on old forecast)

### Day 1

```python
# First day: forecast = first actual value
sales = [100, 110, 105, 120]
alpha = 0.3

forecast_day1 = sales[0]
# = 100

print(f'Day 1: sales={sales[0]}, forecast={forecast_day1}')
```

### Day 2

```python
# Day 2: combine yesterday's sales with yesterday's forecast
forecast_day2 = alpha * sales[1] + (1 - alpha) * forecast_day1
# = 0.3 * 110 + 0.7 * 100
# = 33 + 70
# = 103

print(f'Day 2: sales={sales[1]}, forecast={forecast_day2}')
```

### Day 3

```python
forecast_day3 = alpha * sales[2] + (1 - alpha) * forecast_day2
# = 0.3 * 105 + 0.7 * 103
# = 31.5 + 72.1
# = 103.6

print(f'Day 3: sales={sales[2]}, forecast={forecast_day3:.1f}')
```

### Day 4

```python
forecast_day4 = alpha * sales[3] + (1 - alpha) * forecast_day3
# = 0.3 * 120 + 0.7 * 103.6
# = 36 + 72.52
# = 108.52

print(f'Day 4: sales={sales[3]}, forecast={forecast_day4:.1f}')
```

### Final Forecast for Day 5

```python
forecast_day5 = alpha * sales[3] + (1 - alpha) * forecast_day4
# Wait, we already used sales[3]. The forecast for day 5 is just forecast_day4
# because we do not have day 4 sales yet when forecasting day 5

print(f'Forecast for day 5: {forecast_day4:.1f}')
```

## Try Different Alpha Values

```python
from supplycm.forecasting import single_exponential_smoothing

sales = [100, 110, 105, 120, 115, 130, 125]

for alpha in [0.1, 0.3, 0.5, 0.7, 0.9]:
    forecast = single_exponential_smoothing(sales, alpha=alpha)
    print(f'alpha={alpha}: forecast = {forecast[-1]:.1f}')
```

### What This Shows

- alpha = 0.1: forecast barely moves (too smooth)
- alpha = 0.9: forecast follows sales closely (too jumpy)
- alpha = 0.3: balanced (usually a good starting point)

## When to Use Which Alpha

| Situation | Alpha | Why |
|-----------|-------|-----|
| Stable demand | 0.1 to 0.3 | Do not overreact to changes |
| Trending demand | 0.3 to 0.5 | Follow the trend |
| Rapidly changing | 0.5 to 0.7 | React quickly |
| Very volatile | 0.7 to 0.9 | Mostly use recent data |

## Key Takeaway

Exponential smoothing is like a weighted moving average where:
- Recent days get more weight
- Alpha controls how much weight
- Start with 0.3 and adjust based on your data
