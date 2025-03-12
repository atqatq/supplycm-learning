---
title: "Demand Planning Algorithms | supplycm Algorithm Library"
description: "All 9 demand planning algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, demand, demand planning, supply chain algorithms"
---

# Demand Planning (9 algorithms)

Shape and understand demand: seasons, promotions, substitutions.

**Levels:** 4 beginner · 5 intermediate · 0 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Demand Aggregation](demand_aggregation.md) | Beginner | Aggregation rolls daily demand up into bigger buckets - weekly, monthly, or quarterly |
| 2 | [Demand Disaggregation](demand_disaggregation.md) | Beginner | Disaggregation is the reverse of aggregation: take one big forecast (say, '12,000 units next quarter for the family') and split it across products, regions, or customers using known proportions |
| 3 | [Seasonality Index](seasonality_index.md) | Beginner | A seasonality index tells you how each period compares to the average: 1.0 is ordinary, 1.3 means 30% above typical, 0.7 means 30% below |
| 4 | [Promotional Demand Lift](promotional_demand_lift.md) | Beginner | Lift compares demand during a promotion with the normal baseline: 2.0 means sales doubled |
| 5 | [Cannibalization Effect](cannibalization_effect.md) | Intermediate | When a new product steals sales from your own existing one, that steal is cannibalization |
| 6 | [Stockout Demand Loss](stockout_demand_loss.md) | Intermediate | When shelves go empty, some customers wait, some buy a substitute, and some leave forever |
| 7 | [Demand Sensing](demand_sensing.md) | Intermediate | Sensing blends a statistical forecast with the freshest actuals to correct course mid-period |
| 8 | [ABC-XYZ Demand Classification](demand_class_abc_xyz.md) | Intermediate | This combines two lenses: ABC (how much value a product drives) and XYZ (how predictable its demand is) |
| 9 | [Trend + Seasonal Forecast](trend_seasonal_decomposition_forecast.md) | Intermediate | This splits history into trend (the slow direction) and season (the repeating wiggle), then puts them back together to forecast forward |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_demand.md](../../flashcards/flashcards_demand.md)
- Recall drill: [drills/drill_demand.md](../../drills/drill_demand.md)
