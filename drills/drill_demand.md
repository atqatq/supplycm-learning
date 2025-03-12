---
title: "Recall Drill: Demand Planning | supplycm Learning"
description: "Active-recall drill with answer key covering all 9 supplycm demand planning algorithms."
keywords: "drill, recall, demand, supply chain practice"
---

# Recall Drill: Demand Planning

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Demand Aggregation** (`demand_aggregation`)

1. Why does aggregated demand forecast better than daily demand?
2. Give one thing you LOSE when you aggregate.
3. Your supplier orders monthly but your data is daily. What do you do?

**Demand Disaggregation** (`demand_disaggregation`)

4. Where do the proportions come from?
5. A new SKU has no history. How do you disaggregate to it?
6. Why not forecast each SKU directly?

**Seasonality Index** (`seasonality_index`)

7. What does an index of 1.25 for December mean?
8. How do you deseasonalize?
9. Demand has two peaks a year. What season length fits?

**Promotional Demand Lift** (`promotional_demand_lift`)

10. Why exclude promo weeks from the baseline forecast?
11. Lift was 1.8 last time; order for 1.8 this time?
12. After the promo ends, what often happens to demand?

**Cannibalization Effect** (`cannibalization_effect`)

13. New product sells 200; old product fell 120. Net new demand?
14. Why does cannibalization inflate inventory risk?
15. Name a launch with low cannibalization risk.

**Stockout Demand Loss** (`stockout_demand_loss`)

16. What is substitution rate?
17. Why do repeated stockouts cost more than the math shows?
18. Which products deserve the strictest stockout protection?

**Demand Sensing** (`demand_sensing`)

19. What powers demand sensing?
20. Sensing vs just re-forecasting weekly - difference?
21. When does sensing add the most value?

**ABC-XYZ Demand Classification** (`demand_class_abc_xyz`)

22. What does the AX cell mean and how do you treat it?
23. What about CZ items?
24. Which cell is the most dangerous to ignore?

**Trend + Seasonal Forecast** (`trend_seasonal_decomposition_forecast`)

25. What are the three ingredients of the forecast?
26. What breaks this method?
27. How would you sanity-check its output?

Total: 27 questions.

## Part 2 - Answer key

1. Buckets average out daily randomness - noise cancels, so patterns stand out more.
2. Timing detail within the bucket - daily spikes and hour-of-day patterns vanish.
3. Aggregate to monthly buckets so your forecast matches the decision rhythm.
4. History (past sales shares), current plans (a size's push), or expert judgment - ideally a blend.
5. Borrow proportions from a similar existing product, then update as real sales arrive.
6. Family-level forecasts are more accurate; disaggregation keeps that accuracy while still producing SKU numbers.
7. December typically runs 25% above the average month.
8. Divide each actual by its period's index - what remains is the underlying level and trend.
9. Half a year per cycle - use season_length 6 (or 26 weekly periods per half-year cycle).
10. Otherwise the model 'learns' the promo spike as normal and over-forecasts quiet weeks.
11. Careful - lift depends on discount depth, season, and fatigue. Use history as a guide, then adjust for what's different.
12. A dip - customers stocked up (pantry effect). Plan the trough, not just the peak.
13. 80 units - the 120 that just moved between your own products.
14. You order for 200 new units, but total demand grew only 80 - the extra 120 become slow stock on both lines.
15. A genuinely new use case or new customer segment - e.g., a bike shop adding e-bikes for commuters who never bought bikes before.
16. The share of customers who accept an alternative (another brand, another store, another day) instead of walking away.
17. Loyalty erodes - customers who hit empty shelves twice quietly switch for good.
18. High-margin traffic drivers where customers will not substitute - the reason for milk at the back of the supermarket.
19. Very recent actuals (POS, e-commerce) that arrive faster than the standard monthly re-forecast.
20. Sensing makes small guided adjustments to the existing forecast; re-forecasting rebuilds it from scratch and can swing wildly.
21. When reaction is possible - you can actually change production or shipments inside the period.
22. High value, steady demand - automate replenishment with tight service targets.
23. Low value, erratic demand - simple rules, minimal stock, minimal planner time.
24. AZ - high value but erratic: it hurts the most when wrong and resists automation.
25. Trend (long-run direction), seasonal indices (repeating pattern), and the combination applied to future periods.
26. Sudden level shifts - a new customer or lost contract - that history has never seen.
27. Compare against a simple baseline (last year same period); if the fancy method loses badly, distrust it.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
