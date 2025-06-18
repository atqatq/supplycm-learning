---
title: "Recall Drill: Simulation | supplycm Learning"
description: "Active-recall drill with answer key covering all 2 supplycm simulation algorithms."
keywords: "drill, recall, simulation, supply chain practice"
---

# Recall Drill: Simulation

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Monte Carlo Inventory Simulation** (`monte_carlo_inventory`)

1. Why simulate instead of using a safety-stock formula?
2. What does the seed control?
3. Stockouts happen in 4% of simulated cycles. Options?

**Monte Carlo Risk Simulation** (`monte_carlo_risk`)

4. Why not just multiply probabilities by outcomes?
5. What is a 'tail' outcome and why care?
6. How would you test a dual-sourcing plan here?

Total: 6 questions.

## Part 2 - Answer key

1. Formulas lean on tidy assumptions (normal demand, fixed lead time). Simulation plays out reality, warts and all.
2. The randomness - same seed, same results. Change it and you see a different but statistically similar batch of futures.
3. Raise the reorder point, raise the order quantity, cut lead time, or accept it if the cost is small.
4. Expected values hide the spread. Two plans can share an average while one occasionally ruins you - simulation reveals that.
5. The rare extreme results - they cause stockouts, missed payments, and lost customers, even if the average looks fine.
6. Give the backup supplier a scenario path (delayed, partial) and compare the simulated tail before vs after adding it.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
