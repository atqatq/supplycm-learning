---
title: "Recall Drill: Quality | supplycm Learning"
description: "Active-recall drill with answer key covering all 7 supplycm quality algorithms."
keywords: "drill, recall, quality, supply chain practice"
---

# Recall Drill: Quality

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**DPMO (Defects Per Million Opportunities)** (`dpmo`)

1. What counts as an 'opportunity'?
2. Why multiply to a million?
3. 10 defects, 200 units, 1 opportunity each. DPMO?

**Sigma Level** (`sigma_level`)

4. Roughly how many DPMO is 6 sigma?
5. Is '3 sigma' good enough?
6. Which journey is harder: 2 to 3 sigma, or 5 to 6 sigma?

**Process Capability (Cp)** (`process_capability_cp`)

7. What does Cp ignore that Cpk checks?
8. Cp = 0.8. Can better centering save this process?
9. Spec width 0.4, std 0.1. Cp?

**Process Capability (Cpk)** (`process_capability_cpk`)

10. When is Cpk equal to Cp?
11. Cp 2.0 but Cpk 0.9 - what's wrong?
12. Customer demands Cpk 1.33. You measure 1.1. Options?

**X-Bar Control Chart** (`x_bar_chart`)

13. Control limits vs spec limits - different things?
14. What is a 'special cause'?
15. Sample averages stay in limits but drift upward for 7 points. Problem?

**R Control Chart** (`r_chart`)

16. What exactly does each point on the R chart show?
17. X-bar in control, R chart out of control. What does that mean?
18. Why must you check R before X-bar?

**P Control Chart** (`p_chart`)

19. When do you choose a p chart over X-bar/R?
20. Why do limits change with sample size?
21. A supplier's late-delivery % p chart trends up for 6 weeks. Action?

Total: 21 questions.

## Part 2 - Answer key

1. Any spot where a mistake could happen - a form field, a solder joint, a picking slot.
2. Real samples are small; scaling makes tiny defect rates comparable and discussable.
3. 50,000 - a 5% defect rate expressed per million.
4. 3.4 - near perfection.
5. About 66,800 DPMO - for a hospital pharmacy or an airline that would be a disaster; context decides.
6. 5 to 6 - each sigma step removes an order of magnitude more defects.
7. Centering - Cp assumes perfect centering; Cpk penalizes off-center processes.
8. No - the spread itself is too wide; you must reduce variation, not move the average.
9. 0.4 / 0.6 = about 0.67 - hopeless without cutting variation.
10. When the process mean sits exactly in the middle of the spec limits.
11. The process is badly off-center; recentring alone could restore much of the potential.
12. Cut variation, recentre the mean, or negotiate specs - in that order of preference.
13. Yes! Control limits come from the process voice (its natural variation); specs come from the customer. A process can be 'in control' and still out of spec.
14. Something unusual - a bad material lot, a new operator - that pushes the process beyond its normal wobble.
15. Yes - runs and trends count as out-of-control signals even inside the limits.
16. The range (max - min) of one sample - how scattered that sample was.
17. The average is stable but the spread is not - parts are inconsistent even though the center holds.
18. The X-bar limits are computed FROM the ranges - if spread is unstable, the average chart's limits are built on sand.
19. When the data is pass/fail counts (attribute data), not measurements.
20. Small samples carry more uncertainty, so the limits honestly widen to avoid false alarms.
21. Treat it as a real deterioration signal - start the escalation ladder before it escapes the limits.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
