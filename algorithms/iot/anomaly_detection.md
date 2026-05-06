---
title: "IoT Anomaly Detection | supplycm Algorithm Library"
description: "Plain-English explanation of anomaly_detection from the supplycm IoT & Sensors module, with a runnable Python example and self-check questions."
keywords: "supplycm, iot, anomaly_detection, supply chain, plain english, iot & sensors"
---

# IoT Anomaly Detection

> **Call it:** `from supplycm.iot import anomaly_detection` · **Level:** Intermediate · **You need:** basic arithmetic only

This watches a live data stream and flags readings that stray far from the recent window's norm - measured in standard deviations. It is the smoke detector for machine data: quiet when healthy, loud exactly when something breaks pattern.

**Think of it like this:** A night guard who knows the building's normal sounds - the alarm isn't for noise, it's for sounds that don't belong.

## When to reach for it

- Catching failing sensors, leaks, and unexpected demand shifts live
- Condition monitoring on refrigeration, machines, and stock levels

## Try it with supplycm

```python
from supplycm.iot import anomaly_detection

result = anomaly_detection(data_stream=[20.1, 20.3, 20.2, 20.4, 20.2, 28.0, 20.3], window=5, threshold=3.0)
print(result)
```

You should see something like:

```text
[[5, 28.0]]
```

Flagged (index, value) pairs - the 28.0 stands far outside its neighbors' typical spread; everything else passes silently.

## Check yourself

1. Why compare against a rolling WINDOW, not all history?
2. Threshold 2 vs 4 - alarm personalities?
3. What should an anomaly trigger operationally?

<details>
<summary>Show answers</summary>

1. Because 'normal' drifts - seasons, shifts, and seasons of wear move the baseline; the window follows it.

2. 2 cries often (catches issues early, false alarms too); 4 only screams at genuine extremes - tune by alarm fatigue.

3. A defined response: check the sensor, check the process, log it - unactioned alarms train people to ignore alarms.

</details>

## Try this now

Feed a slow drift (0.5 per reading) with threshold 3 - does the window adapt and hide it? Decide if that's good or dangerous.

---
[← Sensor Data Smoothing](sensor_data_smoothing.md) · [Back to IoT & Sensors library](README.md) · [Real-Time Inventory Monitor →](realtime_inventory_monitor.md)
