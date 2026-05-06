---
title: "Sensor Data Smoothing | supplycm Algorithm Library"
description: "Plain-English explanation of sensor_data_smoothing from the supplycm IoT & Sensors module, with a runnable Python example and self-check questions."
keywords: "supplycm, iot, sensor_data_smoothing, supply chain, plain english, iot & sensors"
---

# Sensor Data Smoothing

> **Call it:** `from supplycm.iot import sensor_data_smoothing` · **Level:** Beginner · **You need:** basic arithmetic only

Raw sensor readings jitter - a temperature of 21.3, 21.4, 25.0, 21.2 is probably not a heat wave. Smoothing blends each reading with recent history (alpha controls memory) so the underlying truth shows while single glitches fade. Same exponential smoothing you know, now applied to machines.

**Think of it like this:** Noise-canceling headphones: the music (real signal) stays, the hiss (sensor noise) fades into the background.

## When to reach for it

- Cleaning temperature, weight, or level sensors before alerting
- Any live dashboard fed by jumpy hardware

## Try it with supplycm

```python
from supplycm.iot import sensor_data_smoothing

result = sensor_data_smoothing(raw_data=[21.3, 21.4, 25.0, 21.2, 21.5], alpha=0.3)
print(result)
```

You should see something like:

```text
[21.3, 21.33, 22.431, 22.0617, 21.8932]
```

The smoothed series barely flinches at the 25.0 glitch - alpha 0.3 lets one reading move the estimate only 30% of the gap.

## Check yourself

1. What does a spike in the smoothed output really mean?
2. Alpha high vs low for sensors?
3. Why not just ignore single readings?

<details>
<summary>Show answers</summary>

1. The sensor moved AND STAYED high for a while - smoothing converts single glitches into sustained signals.

2. High reacts fast (false alarms); low is calm (late alarms) - tune by the cost of each error type.

3. Sometimes a single reading IS the fire - smoothing is for dashboards, alarms often need the raw value too.

</details>

## Try this now

Feed a series with one glitch and one genuine shift; find the alpha that catches the shift but swallows the glitch.

---
[Back to IoT & Sensors library](README.md) · [IoT Anomaly Detection →](anomaly_detection.md)
