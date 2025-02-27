---
title: "Flashcards: Statistics & Accuracy | supplycm Learning"
description: "Spaced-repetition flashcards for all 40 supplycm statistics & accuracy algorithms."
keywords: "flashcards, statistics, supply chain, recall"
---

# Flashcards: Statistics & Accuracy

40 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `descriptive_stats` do? | Descriptive Stats: One call that describes a list of numbers: count, mean (average), median (middle value), standard deviation (how spread out), min, and max. |
| 2 | What does `zscore` do? | Z-Score: A z-score says how many 'usual steps' (standard deviations) a value sits away from the average. |
| 3 | What does `coefficient_of_variation` do? | Coefficient of Variation: The CV is the standard deviation divided by the mean, shown as a percentage. |
| 4 | What does `minmax_scale` do? | Min-Max Scaling: Min-max scaling squeezes all your numbers into a fixed range, usually 0 to 1. |
| 5 | What does `outlier_detection_iqr` do? | Outlier Detection (IQR): This method finds suspicious values using the interquartile range (IQR) - the box where the middle half of your data lives. |
| 6 | What does `skewness` do? | Skewness: Skewness tells you which side your data leans. |
| 7 | What does `kurtosis` do? | Kurtosis: Kurtosis measures how often extreme values show up. |
| 8 | What does `correlation` do? | Correlation: Correlation measures how two things move together, from -1 to +1. |
| 9 | What does `spearman_correlation` do? | Spearman Correlation: Spearman correlation compares rankings instead of raw values. |
| 10 | What does `r_squared` do? | R-Squared: R-squared says how much of the movement in your actuals your forecast or line managed to explain, from 0 to 1. |
| 11 | What does `coefficient_of_determination` do? | Coefficient of Determination: This is R-squared's other name, computed between two series: it answers 'what fraction of the variation does one series explain about the other?'. |
| 12 | What does `adjusted_r_squared` do? | Adjusted R-Squared: Every extra factor you throw into a model makes plain R-squared look better, even when the factor is useless. |
| 13 | What does `confidence_interval_mean` do? | Confidence Interval for a Mean: A confidence interval wraps a range around your average: 'true demand is likely between X and Y'. |
| 14 | What does `bootstrap_confidence_interval` do? | Bootstrap Confidence Interval: The bootstrap builds confidence intervals by repeatedly resampling your own data (with a fixed seed so results repeat). |
| 15 | What does `moving_average_smooth` do? | Moving Average Smoothing: A moving average replaces each point with the average of its neighbors, smoothing out day-to-day noise so the underlying trend shows. |
| 16 | What does `exponential_smooth` do? | Exponential Smoothing (Statistics): This smoother weights recent points more than old ones, with alpha controlling the memory: high alpha = reactive, low alpha = calm. |
| 17 | What does `anova_one_way` do? | ANOVA (One-Way F-Statistic): ANOVA asks whether several groups really differ in their average, or whether the differences are just noise. |
| 18 | What does `f_test_variance` do? | F-Test for Variances: Sometimes the question is not whether averages differ, but whether consistency differs. |
| 19 | What does `t_test_one_sample` do? | One-Sample T-Statistic: This tests whether your sample's average differs from a claimed value. |
| 20 | What does `t_test_two_sample` do? | Two-Sample T-Statistic: Compares the averages of two groups and returns a t-statistic - near 0 means the groups are indistinguishable, large means one is genuinely higher or lower than the other. |
| 21 | What does `tracking_signal_threshold` do? | Tracking Signal Threshold Check: A tracking signal watches whether your forecast is persistently too high or too low. |
| 22 | What does `bias` do? | Bias (Mean Error): Bias is the average of (actual minus forecast). |
| 23 | What does `mae` do? | MAE (Mean Absolute Error): MAE is the average miss, ignoring direction: forecast 110 when actual was 100 counts as 10, whether high or low. |
| 24 | What does `mse` do? | MSE (Mean Squared Error): MSE squares each error before averaging, which punishes big misses much harder than small ones. |
| 25 | What does `rmse` do? | RMSE (Root Mean Squared Error): RMSE is the square root of MSE. |
| 26 | What does `mape` do? | MAPE (Mean Absolute Percentage Error): MAPE expresses error as a percentage of actual sales, so it works across products of different sizes. |
| 27 | What does `smape` do? | SMAPE (Symmetric MAPE): SMAPE divides the error by the average of actual and forecast instead of just the actual. |
| 28 | What does `mean_percentage_error` do? | MPE (Mean Percentage Error): MPE is like MAPE but keeps the sign, so it shows systematic percentage-level tilt: positive means under-forecasting in percent terms, negative means over-forecasting. |
| 29 | What does `percent_bias` do? | Percent Bias (PBIAS): PBIAS sums ALL errors and divides by the sum of all actuals, giving one overall percentage tilt. |
| 30 | What does `mase` do? | MASE (Mean Absolute Scaled Error): MASE compares your forecast against the naive 'copy yesterday' forecast. |
| 31 | What does `forecast_value_added` do? | Forecast Value Added (FVA): FVA measures whether your whole forecasting process (with its meetings, judgments, and overrides) actually beats a naive baseline. |
| 32 | What does `diebold_mariano_test` do? | Diebold-Mariano Test: Two forecasts, one winner - but is the win real or luck? The DM test compares their errors and returns a statistic: far from 0 means one forecast is genuinely better, near 0 means the difference is noise. |
| 33 | What does `anderson_darling_test` do? | Anderson-Darling Statistic: Checks whether your data plausibly follows a bell-curve (normal) shape, paying special attention to the tails. |
| 34 | What does `shapiro_wilk_approx` do? | Shapiro-Wilk Approximation: Another bell-curve check, famous for being sensitive even with small samples. |
| 35 | What does `jarque_bera_test` do? | Jarque-Bera Statistic: A shape test built from skewness (lean) and kurtosis (shockiness) together. |
| 36 | What does `chi_square_goodness_of_fit` do? | Chi-Square Goodness of Fit: Compares observed counts against expected counts across categories. |
| 37 | What does `kolmogorov_smirnov_test` do? | Kolmogorov-Smirnov Test (One Sample): KS compares the whole shape of your data to a reference pattern - it walks along the sorted values and measures the biggest gap between what you have and what you'd expect. |
| 38 | What does `kolmogorov_smirnov_two_sample` do? | KS Test (Two Samples): Asks whether two batches of data come from the same overall pattern - not just the same average. |
| 39 | What does `mann_whitney_u` do? | Mann-Whitney U: A rank-based contest between two groups: pool all values, rank them, and see whether one group dominates the top ranks. |
| 40 | What does `wilcoxon_signed_rank` do? | Wilcoxon Signed-Rank: Tests paired before/after differences: rank the sizes of the changes and see whether positive or negative changes dominate. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
