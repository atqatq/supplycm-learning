---
title: "IoT Data Aggregation | supplycm Algorithm Library"
description: "Plain-English explanation of iot_data_aggregation from the supplycm IoT & Sensors module, with a runnable Python example and self-check questions."
keywords: "supplycm, iot, iot_data_aggregation, supply chain, plain english, iot & sensors"
---

# IoT Data Aggregation

> **Call it:** `from supplycm.iot import iot_data_aggregation` · **Level:** Intermediate · **You need:** basic arithmetic only

Sensors talk constantly - hundreds of readings per hour, most redundant. This folds the stream into time buckets (average per 10 minutes, say), producing a clean series for dashboards, trends, and the anomaly detector's input. Less noise, same story, smaller data.

**Think of it like this:** A stenographer summarizing a rambling meeting into clean minutes: every important point kept, every throat-clearing dropped.

## When to reach for it

- Reducing high-frequency sensor streams to dashboard-friendly buckets
- Preparing clean series for smoothing and anomaly detection

## Try it with supplycm

```python
from supplycm.iot import iot_data_aggregation

result = iot_data_aggregation(timestamps=[0, 1, 2, 11, 12, 21, 22], values=[20.1, 20.3, 20.2, 21.0, 21.2, 22.0, 22.1], window_size=10)
print(result)
```

You should see something like:

```text
[{'start': 0, 'end': 11, 'mean': 20.2, 'min': 20.1, 'max': 20.3, 'count': 3}, {'start': 11, 'end': 21, 'mean': 21.1, 'min': 21.0, 'max': 21.2, 'count': 2}, {'start': 21, 'end': 22, 'mean': 22.05, 'min': 22.0, 'max': 22.1, 'count': 2}]
```

One summary per 10-unit window - three buckets replace seven readings; trends survive, jitter doesn't.

## Check yourself

1. What's lost when you aggregate?
2. Which bucket statistic fits inventory sensors?
3. How does bucket size trade off insight?

<details>
<summary>Show answers</summary>

1. Within-bucket detail - a spike and a dip inside one window can average into a boring number; alarm logic may need raw feeds.

2. Average for levels, MAXIMUM for temperatures (the excursion matters, not the mean) - pick the statistic that matches the risk.

3. Small buckets keep detail but stay noisy; large buckets smooth but delay - match the size to your decision cadence.

</details>

## Try this now

Aggregate a noisy hourly stream into 30-minute buckets using max; show how a short spike survives the fold.

---
[← Real-Time Inventory Monitor](realtime_inventory_monitor.md) · [Back to IoT & Sensors library](README.md)
