---
title: "Recall Drill: Statistics & Accuracy | supplycm Learning"
description: "Active-recall drill with answer key covering all 40 supplycm statistics & accuracy algorithms."
keywords: "drill, recall, statistics, supply chain practice"
---

# Recall Drill: Statistics & Accuracy

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Descriptive Stats** (`descriptive_stats`)

1. What is the difference between mean and median?
2. Which is more robust to one crazy day: mean or median?
3. What does a large standard deviation tell you?

**Z-Score** (`zscore`)

4. A z-score of 0 means what?
5. Is a z-score of +2.8 or +0.4 more unusual?
6. Why are z-scores useful for comparing two different products?

**Coefficient of Variation** (`coefficient_of_variation`)

7. Product A: mean 100, std 10. Product B: mean 50, std 10. Which has the higher CV?
8. Why not just compare standard deviations directly?
9. What CV would you expect for a fast-selling staple like milk?

**Min-Max Scaling** (`minmax_scale`)

10. What do the min and max values always become?
11. Does scaling change the order or spacing pattern of the data?
12. Two suppliers: price 0.9 (scaled), defect rate 0.1 (scaled). Who is better?

**Outlier Detection (IQR)** (`outlier_detection_iqr`)

13. What does IQR stand for and what does it measure?
14. A one-day spike that was a real promotion - should it be removed as an outlier?
15. Why clean outliers before forecasting?

**Skewness** (`skewness`)

16. Positive skew means the tail points which way?
17. For strongly skewed demand, is mean or median the better 'typical day'?
18. Give a real product likely to have positive demand skew.

**Kurtosis** (`kurtosis`)

19. High kurtosis means what kind of extremes?
20. Is kurtosis about the direction of the tail (left/right)?
21. Why should a risk manager love kurtosis?

**Correlation** (`correlation`)

22. Correlation of -0.9 means what?
23. Does a strong correlation prove one causes the other?
24. Why should forecasters hunt for correlated drivers?

**Spearman Correlation** (`spearman_correlation`)

25. When would you prefer Spearman over normal correlation?
26. Two series ranked exactly opposite get which Spearman value?
27. A store's daily sales rank correlates 0.95 with daily visitors' rank. What should management consider?

**R-Squared** (`r_squared`)

28. R-squared of 0 means what?
29. Is a high R-squared alone proof the forecast is good?
30. Forecast A: R-squared 0.9. Forecast B: 0.4. Which tracks history better?

**Coefficient of Determination** (`coefficient_of_determination`)

31. If correlation is 0.5, what is the coefficient of determination?
32. Explain R-squared 0.25 in manager language.
33. What value would a perfect predictor have?

**Adjusted R-Squared** (`adjusted_r_squared`)

34. Why does plain R-squared never decrease when you add a factor?
35. You add a factor and adjusted R-squared drops. What does that tell you?
36. When do R-squared and adjusted R-squared converge?

**Confidence Interval for a Mean** (`confidence_interval_mean`)

37. What three things control the width of the interval?
38. Does a 95% interval mean there is a 95% chance the mean is inside this exact interval?
39. You want a narrower interval. Name two honest ways.

**Bootstrap Confidence Interval** (`bootstrap_confidence_interval`)

40. Why does the bootstrap need a seed?
41. What is 'resampling with replacement'?
42. When would you prefer bootstrap over a formula-based interval?

**Moving Average Smoothing** (`moving_average_smooth`)

43. What happens if you increase the window from 3 to 12?
44. Why do the early positions lack a full average?
45. Name one risk of over-smoothing.

**Exponential Smoothing (Statistics)** (`exponential_smooth`)

46. What does alpha = 0.9 vs alpha = 0.1 change?
47. Why is it called 'exponential'?
48. You notice a level shift last week. Should alpha go up or down?

**ANOVA (One-Way F-Statistic)** (`anova_one_way`)

49. An F-statistic near 1 suggests what?
50. Why not just run several two-group tests instead?
51. What should you check before trusting a big F?

**F-Test for Variances** (`f_test_variance`)

52. An F ratio of exactly 1 means what?
53. Which group is more unpredictable if F is 9?
54. Why does higher variance force higher safety stock?

**One-Sample T-Statistic** (`t_test_one_sample`)

55. t near 0 means what?
56. Does a bigger sample make the same gap produce a bigger t?
57. You promised customers 5-day delivery; sampled actuals give t = +6. Action?

**Two-Sample T-Statistic** (`t_test_two_sample`)

58. t = -0.2 vs t = -5.2: which shows a clearer difference?
59. Name the assumptions behind trusting this test.
60. You pilot a new picking method. Half the team uses it. What do you compare?

**Tracking Signal Threshold Check** (`tracking_signal_threshold`)

61. A tracking signal of +5 means the forecast has been doing what?
62. Why is a constant small error worse than alternating errors?
63. What is the first response when the alarm fires?

**Bias (Mean Error)** (`bias`)

64. Bias of -8 means the forecast has been doing what?
65. Can errors be large while bias is 0?
66. You fix a positive bias by just adding +5 to every forecast. What could go wrong?

**MAE (Mean Absolute Error)** (`mae`)

67. Why take absolute values before averaging?
68. MAE of 12 on demand of 1,200 vs on demand of 15 - which is worse?
69. If MAE suddenly doubles, what do you do?

**MSE (Mean Squared Error)** (`mse`)

70. Why does one huge error dominate MSE?
71. MSE vs MAE: which to use for a stable, low-stakes product?
72. What is RMSE's relationship to MSE?

**RMSE (Root Mean Squared Error)** (`rmse`)

73. Why take a square root at all?
74. Which is always bigger: MAE or RMSE?
75. RMSE is 3x MAE. What does that reveal?

**MAPE (Mean Absolute Percentage Error)** (`mape`)

76. Why does MAPE break when actuals are near zero?
77. A fast mover and a slow mover both show MAPE 30%. Same pain?
78. What MAPE target is realistic for stable products vs erratic ones?

**SMAPE (Symmetric MAPE)** (`smape`)

79. Why 'symmetric'?
80. Is a SMAPE of 40% bad?
81. When would you still prefer plain MAPE?

**MPE (Mean Percentage Error)** (`mean_percentage_error`)

82. MPE near zero but MAPE high - what does that mean?
83. Why can MPE mislead with mixed big and small actuals?
84. MPE is -12%. Action?

**Percent Bias (PBIAS)** (`percent_bias`)

85. How does PBIAS differ from MAPE?
86. Which is closer to financial impact?
87. PBIAS = -5% on annual demand of 1M units means what?

**MASE (Mean Absolute Scaled Error)** (`mase`)

88. MASE of 1.4 means what?
89. Why is MASE called 'scaled'?
90. Your MAPE looks great but MASE is 1.2. Trust which one?

**Forecast Value Added (FVA)** (`forecast_value_added`)

91. FVA is -3%. What should leadership consider?
92. Which naive baseline is usually used?
93. Who should see FVA regularly?

**Diebold-Mariano Test** (`diebold_mariano_test`)

94. DM near 0 means what?
95. You see DM = +3 consistently favoring model A. Action?
96. Why not just compare MAPE once and decide?

**Anderson-Darling Statistic** (`anderson_darling_test`)

97. Why do tails matter so much in supply chains?
98. Data fails the normality check. Now what?
99. Is a small statistic a guarantee the data is normal?

**Shapiro-Wilk Approximation** (`shapiro_wilk_approx`)

100. What does a statistic near 1 suggest?
101. Why does small-sample sensitivity matter in supply chains?
102. Data is skewed right. Which safety-stock approach fits better?

**Jarque-Bera Statistic** (`jarque_bera_test`)

103. Which two ingredients drive the JB statistic?
104. Symmetric but shock-prone data: will JB flag it?
105. JB is high. Name two supply-chain consequences.

**Chi-Square Goodness of Fit** (`chi_square_goodness_of_fit`)

106. What do 'observed' and 'expected' mean here?
107. Does chi-square care about the size of counts?
108. Saturday demand keeps beating the plan. Which test flags it?

**Kolmogorov-Smirnov Test (One Sample)** (`kolmogorov_smirnov_test`)

109. What makes KS different from chi-square?
110. KS statistic is large. Conclusion?
111. When is a shape check more important than an average check?

**KS Test (Two Samples)** (`kolmogorov_smirnov_two_sample`)

112. What question does the two-sample KS answer?
113. Two batches share an average but KS is large. What is going on?
114. Before trusting a simulation for planning, what should you run?

**Mann-Whitney U** (`mann_whitney_u`)

115. What does U actually count?
116. Why use ranks instead of raw values?
117. U strongly favors group B. Verdict?

**Wilcoxon Signed-Rank** (`wilcoxon_signed_rank`)

118. What makes a test 'paired'?
119. A change of -1 vs -10: same rank weight?
120. You changed the packing process in 8 stores (paired data). W+ is strongly positive. Conclusion?

Total: 120 questions.

## Part 2 - Answer key

1. Mean = add everything and divide by the count. Median = the middle value when you sort the numbers.
2. The median. One huge value can drag the mean far away, but barely moves the median.
3. The numbers swing widely around the average - demand is hard to pin down, so plans need more buffer.
4. The value equals the average - completely typical.
5. +2.8. The further from 0, the more unusual the value.
6. They put both on the same surprise scale, even if one sells 10 units and the other sells 10,000.
7. B. Same spread but smaller average, so the noise matters more relative to size (20% vs 10%).
8. Std ignores scale: a std of 10 is tiny for sales of 1,000 but huge for sales of 20. CV puts both on a fair footing.
9. Low, maybe under 0.2 - people buy milk steadily, whatever else happens.
10. 0 and 1 (the ends of the target range).
11. No - it only stretches or squeezes the ruler, the pattern stays identical.
12. It depends on direction: for price, low is good; for defects, low is good. Always note which way each score points before combining them.
13. Interquartile range: the span between the 25th and 75th percentiles, i.e. where the middle 50% of values live.
14. Usually no. Outliers from known causes (promos) should be explained or handled separately, not silently deleted.
15. Because methods built on averages get dragged by extreme values and will over-forecast future normal days.
16. To the right - toward the occasional large values.
17. The median - the mean gets pulled by the tail.
18. Umbrellas: steady low sales with rare storm-day surges.
19. Rare but sharp ones - long stretches of calm punctuated by big spikes.
20. No - that is skewness. Kurtosis is about how heavy the tails are in general.
21. It reveals products that look stable on average but hide shock risk in the tails.
22. The two move almost perfectly in opposite directions - when one goes up, the other goes down.
23. No. Both may be driven by a third factor (like season). Correlation is a clue, not proof.
24. If you can predict the driver (like temperature), you inherit predictive power for your demand.
25. When only the order matters, or when outliers would distort the raw-value correlation.
26. -1.
27. Foot traffic drives sales - so forecasting visitors may help forecast sales.
28. The model explains nothing beyond just predicting the overall average.
29. Not alone - it can look great on history and still fail forward. Always also check out-of-sample error.
30. A - it follows 90% of the pattern vs 40%.
31. 0.25 - you square it. Half the correlation becomes a quarter of the explanation.
32. Only about a quarter of the variation is explained; three quarters is unexplained noise or other factors.
33. 1 (100% of variation explained).
34. It mechanically rewards any extra variable, even noise. That is why the adjusted version exists.
35. The factor was not worth its complexity - drop it.
36. When the sample size is large relative to the number of factors.
37. How spread out the data is, how many points you have, and the confidence level you demand.
38. Loosely: if you repeated the whole process many times, about 95% of such intervals would capture the true mean.
39. Collect more data, or accept a lower confidence level (e.g., 90% instead of 99%).
40. It uses random resampling; the seed makes results reproducible run after run.
41. Drawing new samples from your data where each drawn value goes back into the pool and can be drawn again.
42. When data is skewed, has outliers, or the sample is small and the standard formula is shaky.
43. The line gets smoother but reacts more slowly to real changes.
44. At the start there are not enough neighbors yet to fill a full window.
45. You can hide real turning points until it is too late to react.
46. 0.9 chases recent points closely (jumpy); 0.1 changes slowly (smooth but laggy).
47. The weights on older points shrink by a constant factor each step back, decaying exponentially.
48. Up - more weight on recent data lets the smoother catch up faster.
49. The between-group differences are about what noise alone would produce - probably no real difference.
50. Repeated tests pile up false alarms; ANOVA compares all groups in one fair test.
51. That each group has enough data and no wild outliers - F is sensitive to extremes.
52. Both groups have the same variance - equally consistent.
53. Whose variance sits on top of the division - the much more spread-out group.
54. You must buffer against a wider range of outcomes, so you hold more 'just in case' stock.
55. The sample average sits close to the claimed value.
56. Yes - more data makes the same difference more statistically convincing.
57. The real average is far above 5 - fix the promise or fix the process.
58. The -5.2 - far from 0 means the gap is much larger than noise could explain.
59. Reasonably well-behaved (not wildly skewed) data, few outliers, and enough points per group.
60. Picks-per-hour of both groups with a two-sample test - and also check consistency, not just the average.
61. Persistently UNDER-forecasting - actuals keep beating it in the same direction.
62. Alternating errors cancel out; a constant push in one direction compounds into big inventory or service mistakes.
63. Investigate for a level shift (new customer, promo, price change) and re-fit or adjust the forecast.
64. Over-forecasting by 8 units on average - you are planning for more demand than shows up.
65. Yes - big misses in opposite directions cancel out. That is why you track bias AND a size metric like MAPE.
66. The underlying pattern is still unexplained; the offset may not hold as conditions change. Fix causes, not symptoms.
67. So opposite errors cancel each other instead of hiding the real size of the miss.
68. The 15-unit product: 12 is 80% of typical sales, while it is just 1% for the big one. Percentages matter.
69. Investigate: something changed - season, customer mix, or the model broke. Check bias too for direction.
70. Squaring turns a 60 miss into 3,600 while a 5 miss is only 25 - the big miss outweighs dozens of small ones.
71. MAE - it reflects typical error without over-dramatizing rare spikes.
72. RMSE is the square root of MSE, bringing the error back into the original units.
73. Squaring distorts units; the root brings errors back to 'units of demand' so people can act on them.
74. RMSE is never smaller - the extra weight on big errors keeps it at or above MAE.
75. Errors are lumpy - a few big misses dominate. Investigate those days rather than the average day.
76. Dividing by a tiny actual explodes the percentage - one unit of error on sales of 2 is 50%.
77. No - 30% of a huge product can hurt the business far more. Pair MAPE with volume-weighted views.
78. Stable staples: often under 10%. Seasonal or slow movers: 25-50% may already be good.
79. Actual and forecast share the denominator equally, so over- and under-forecasting of the same size score the same.
80. Depends on the product and industry - for erratic or slow movers it can be acceptable; compare against a naive baseline.
81. When your audience expects it - it remains the business standard - or when actuals are never near zero.
82. Errors are large but cancel out in direction - you are inconsistent rather than systematically tilted.
83. Small actuals produce huge percentage swings that can dominate the average.
84. Forecasts run about 12% high on average - trim plans or recalibrate the model upward on demand.
85. MAPE averages per-day percentages (each day counts equally); PBIAS weights by volume (big days count more).
86. PBIAS - money scales with units, and PBIAS weights units.
87. You planned about 50,000 units of phantom demand - real money tied up in stock.
88. Your method is 40% worse than the naive baseline - time to simplify or re-fit.
89. The errors are divided by the naive method's typical error, stripping out product scale.
90. Be suspicious - relative to its own history, the forecast is losing to 'copy yesterday'. MASE catches that trap.
91. The process destroys value vs a naive forecast - simplify, or find which step (override? data?) hurts.
92. Often 'no change from last period'; seasonal products may use 'same period last year'.
93. The S&OP team and executives - it is the cheapest way to keep the process honest.
94. The two forecasts are statistically indistinguishable - pick either, or blend them.
95. Adopt A, but keep monitoring - edges can fade as conditions change.
96. One sample can flatter either method; DM asks whether the gap would survive repeated testing.
97. Stockouts and surpluses live in the tails - the rare days. Get the tails wrong and your buffers are wrong.
98. Use methods that do not assume a bell curve - simulations, bootstrap intervals, or non-normal distributions.
99. No - just 'no evidence against it'. Real demand is often at least a bit lumpy.
100. The data looks consistent with a normal bell curve.
101. New SKUs and short histories are everywhere; you still need a shape check with 12 data points.
102. One that respects the skew - e.g., simulation or quantile-based buffers - rather than plain normal formulas.
103. Skewness and kurtosis - lean and shockiness of the distribution.
104. Yes - kurtosis alone can push the statistic high even with zero skew.
105. Safety stocks tuned to a normal curve will miss the real tails; percentile promises (like 95% service) will be off.
106. Observed = what actually happened; expected = what your assumption predicts should happen.
107. Yes - it works on counts, so you need enough volume per category for the test to mean anything.
108. Chi-square across weekdays would show one category contributing a big chunk of the statistic.
109. KS works on the full ordered shape and needs no arbitrary category bins.
110. The data's overall shape does not match the reference - dig into where the gap opens.
111. When tails drive decisions - safety stock, service levels, disaster planning.
112. 'Could these two batches come from the same underlying pattern?' - about whole shape, not just averages.
113. Their spread or shape differs - e.g., one is calm, one is spiky - which averages hide.
114. A two-sample KS (or similar shape check) between simulated and real demand.
115. Ranks: how often a value from one group beats a value from the other.
116. Outliers and skew distort averages; ranks only care about order, which is more robust.
117. B tends to run higher - plan differently for it (more capacity, bigger buffers, separate forecast).
118. Each observation has a natural partner: same store before/after, same machine old/new.
119. No - ranks use the SIZE of changes: bigger absolute changes rank higher.
120. The change tended to improve the measured outcome - consider a rollout.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
