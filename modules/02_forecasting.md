# Module 2: Predicting the Future (Forecasting)

## The Big Idea

Forecasting means guessing what will happen next based on what happened before.

If you sold 100 ice creams yesterday, 110 today, and 105 the day before, you can guess you will sell about 105 tomorrow.

That is forecasting.

## Why Does It Matter?

Imagine you own a bakery. You need to bake bread every morning.

- Bake too much: bread goes stale, you lose money
- Bake too little: customers go home empty-handed, you lose sales

A good forecast helps you bake just the right amount.

## The Simplest Forecast: Naive Method

The easiest forecast says: "Tomorrow will be the same as today."

If you sold 50 cakes today, predict 50 for tomorrow.

### Try it with supplycm

```python
from supplycm.forecasting import naive_forecast

sales = [40, 45, 42, 50, 48]
forecast = naive_forecast(sales)
print(forecast)
# Output: [None, 40, 45, 42, 50]
# The forecast for each day is the previous day's sales
```

The first value is `None` because we do not have a previous day to copy from.

## Better Forecast: Moving Average

Instead of just copying yesterday, average the last few days.

If you sold 40, 45, and 42 in the last 3 days, the average is (40 + 45 + 42) / 3 = 42.3.

### Try it with supplycm

```python
from supplycm.forecasting import simple_moving_average

sales = [40, 45, 42, 50, 48, 55]
forecast = simple_moving_average(sales, window=3)
print(forecast)
# Output: [None, None, 42.33, 45.67, 46.67, 51.0]
```

The first two are `None` because we need 3 days to make an average.

## Even Better: Exponential Smoothing

This method says: "Recent days matter more than old days."

It is like a moving average, but yesterday counts more than last week.

### Try it with supplycm

```python
from supplycm.forecasting import single_exponential_smoothing

sales = [40, 45, 42, 50, 48]
forecast = single_exponential_smoothing(sales, alpha=0.3)
print(forecast)
# alpha controls how much weight to give recent days
# Higher alpha (closer to 1) = care more about recent days
```

## When Things Have a Pattern: Seasonality

Some things sell more at certain times:

- Ice cream sells more in summer
- Toys sell more before holidays
- Umbrellas sell more when it rains

If your data has a repeating pattern, use Holt-Winters method.

### Try it with supplycm

```python
from supplycm.forecasting import holt_winters

# 8 months of sales with a 4-month pattern
sales = [100, 120, 130, 90, 105, 125, 135, 95]
level, trend, seasonal = holt_winters(sales, season_length=4)
print(f"Current level: {level[-1]:.1f}")
```

## How Good Is Your Forecast?

You need to check if your forecast is close to reality. The most common way is MAPE (Mean Absolute Percentage Error).

MAPE tells you, on average, how far off your forecast was as a percentage.

### Try it with supplycm

```python
from supplycm.statistics import mape

actual = [100, 110, 105]
forecast = [102, 108, 107]

error = mape(actual, forecast)
print(f"Your forecast is off by {error:.1f}% on average")
```

- Less than 10%: great forecast
- 10% to 20%: okay forecast
- More than 20%: needs improvement

## Quick Quiz

1. If you sold 30, 35, 32 yesterday, today, and the day before, what is the 3-day moving average?
2. Why would you use exponential smoothing instead of a moving average?
3. What does MAPE stand for?

<details>
<summary>Click to reveal answers</summary>

1. (30 + 35 + 32) / 3 = 32.3
2. Because recent data is more important than old data
3. Mean Absolute Percentage Error

</details>

## Exercise

1. Install supplycm: `pip install supplycm`
2. Make up sales data for 7 days
3. Forecast day 8 using:
   - Naive method
   - 3-day moving average
   - Exponential smoothing (alpha = 0.3)
4. Which forecast feels right to you? Why?

## Key Words

- **Forecast**: A guess about the future based on the past
- **Naive method**: Tomorrow equals today
- **Moving average**: Average of the last N days
- **Exponential smoothing**: Weighted average where recent days count more
- **Seasonality**: A repeating pattern in data
- **MAPE**: A measure of forecast accuracy (percentage)

## What's Next?

Now you can predict demand. The next lesson teaches you how much to order based on that prediction.

Next: [Module 3 - Having the Right Amount of Stuff (Inventory)](03_inventory.md)
