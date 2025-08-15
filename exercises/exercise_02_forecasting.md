# Exercise 2: Forecasting

## Problem

You sell lemonade. Here are your sales for the last 7 days:

| Day | Sales |
|-----|-------|
| Mon | 45 |
| Tue | 52 |
| Wed | 48 |
| Thu | 60 |
| Fri | 75 |
| Sat | 90 |
| Sun | 85 |

### Tasks

1. Forecast Monday's sales using the naive method
2. Forecast using a 3-day moving average
3. Forecast using exponential smoothing (alpha = 0.3)
4. Which forecast do you trust most? Why?

## Your Answer

Write your calculations here:

```
Naive forecast: ___

3-day moving average: ___

Exponential smoothing: ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.forecasting import naive_forecast, simple_moving_average, single_exponential_smoothing

sales = [45, 52, 48, 60, 75, 90, 85]

# 1. Naive: Monday = Sunday = 85
naive = naive_forecast(sales)
print(f"Naive forecast: {naive[-1]}")

# 2. 3-day moving average: (75 + 90 + 85) / 3 = 83.3
sma = simple_moving_average(sales, window=3)
print(f"3-day SMA: {sma[-1]:.1f}")

# 3. Exponential smoothing
ses = single_exponential_smoothing(sales, alpha=0.3)
print(f"SES: {ses[-1]:.1f}")
```

### Expected Results

1. Naive: 85 (copy last day)
2. 3-day SMA: 83.3 (average of last 3 days)
3. SES: about 72.5 (weighted average, recent days count more)

### Which to trust?

The 3-day SMA or SES would be best. The naive method ignores the upward trend. SES captures the trend while smoothing noise.

</details>
