---
title: "Recall Drill: IoT & Sensors | supplycm Learning"
description: "Active-recall drill with answer key covering all 4 supplycm iot & sensors algorithms."
keywords: "drill, recall, iot, supply chain practice"
---

# Recall Drill: IoT & Sensors

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Sensor Data Smoothing** (`sensor_data_smoothing`)

1. What does a spike in the smoothed output really mean?
2. Alpha high vs low for sensors?
3. Why not just ignore single readings?

**IoT Anomaly Detection** (`anomaly_detection`)

4. Why compare against a rolling WINDOW, not all history?
5. Threshold 2 vs 4 - alarm personalities?
6. What should an anomaly trigger operationally?

**Real-Time Inventory Monitor** (`realtime_inventory_monitor`)

7. What makes this better than a nightly stock report?
8. Why do safety stocks enter the urgency call?
9. What data quality risk grows with live monitoring?

**IoT Data Aggregation** (`iot_data_aggregation`)

10. What's lost when you aggregate?
11. Which bucket statistic fits inventory sensors?
12. How does bucket size trade off insight?

Total: 12 questions.

## Part 2 - Answer key

1. The sensor moved AND STAYED high for a while - smoothing converts single glitches into sustained signals.
2. High reacts fast (false alarms); low is calm (late alarms) - tune by the cost of each error type.
3. Sometimes a single reading IS the fire - smoothing is for dashboards, alarms often need the raw value too.
4. Because 'normal' drifts - seasons, shifts, and seasons of wear move the baseline; the window follows it.
5. 2 cries often (catches issues early, false alarms too); 4 only screams at genuine extremes - tune by alarm fatigue.
6. A defined response: check the sensor, check the process, log it - unactioned alarms train people to ignore alarms.
7. Speed: the breach triggers NOW, while the nightly report tells you yesterday's news after the stockout.
8. A breach far above safety stock is routine; a breach at the floor is an emergency - distance from the floor sets priority.
9. Sensor drift and phantom readings - calibrate against cycle counts or the system will confidently order nonsense.
10. Within-bucket detail - a spike and a dip inside one window can average into a boring number; alarm logic may need raw feeds.
11. Average for levels, MAXIMUM for temperatures (the excursion matters, not the mean) - pick the statistic that matches the risk.
12. Small buckets keep detail but stay noisy; large buckets smooth but delay - match the size to your decision cadence.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
