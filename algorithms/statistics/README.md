---
title: "Statistics & Accuracy Algorithms | supplycm Algorithm Library"
description: "All 40 statistics & accuracy algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, statistics, statistics & accuracy, supply chain algorithms"
---

# Statistics & Accuracy (40 algorithms)

Measure things fairly: averages, spread, and forecast error.

**Levels:** 12 beginner · 16 intermediate · 12 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Descriptive Stats](descriptive_stats.md) | Beginner | One call that describes a list of numbers: count, mean (average), median (middle value), standard deviation (how spread out), min, and max |
| 2 | [Z-Score](zscore.md) | Beginner | A z-score says how many 'usual steps' (standard deviations) a value sits away from the average |
| 3 | [Coefficient of Variation](coefficient_of_variation.md) | Beginner | The CV is the standard deviation divided by the mean, shown as a percentage |
| 4 | [Min-Max Scaling](minmax_scale.md) | Beginner | Min-max scaling squeezes all your numbers into a fixed range, usually 0 to 1 |
| 5 | [Outlier Detection (IQR)](outlier_detection_iqr.md) | Beginner | This method finds suspicious values using the interquartile range (IQR) - the box where the middle half of your data lives |
| 6 | [Skewness](skewness.md) | Intermediate | Skewness tells you which side your data leans |
| 7 | [Kurtosis](kurtosis.md) | Advanced | Kurtosis measures how often extreme values show up |
| 8 | [Correlation](correlation.md) | Beginner | Correlation measures how two things move together, from -1 to +1 |
| 9 | [Spearman Correlation](spearman_correlation.md) | Intermediate | Spearman correlation compares rankings instead of raw values |
| 10 | [R-Squared](r_squared.md) | Intermediate | R-squared says how much of the movement in your actuals your forecast or line managed to explain, from 0 to 1 |
| 11 | [Coefficient of Determination](coefficient_of_determination.md) | Intermediate | This is R-squared's other name, computed between two series: it answers 'what fraction of the variation does one series explain about the other?' |
| 12 | [Adjusted R-Squared](adjusted_r_squared.md) | Advanced | Every extra factor you throw into a model makes plain R-squared look better, even when the factor is useless |
| 13 | [Confidence Interval for a Mean](confidence_interval_mean.md) | Intermediate | A confidence interval wraps a range around your average: 'true demand is likely between X and Y' |
| 14 | [Bootstrap Confidence Interval](bootstrap_confidence_interval.md) | Intermediate | The bootstrap builds confidence intervals by repeatedly resampling your own data (with a fixed seed so results repeat) |
| 15 | [Moving Average Smoothing](moving_average_smooth.md) | Beginner | A moving average replaces each point with the average of its neighbors, smoothing out day-to-day noise so the underlying trend shows |
| 16 | [Exponential Smoothing (Statistics)](exponential_smooth.md) | Beginner | This smoother weights recent points more than old ones, with alpha controlling the memory: high alpha = reactive, low alpha = calm |
| 17 | [ANOVA (One-Way F-Statistic)](anova_one_way.md) | Intermediate | ANOVA asks whether several groups really differ in their average, or whether the differences are just noise |
| 18 | [F-Test for Variances](f_test_variance.md) | Advanced | Sometimes the question is not whether averages differ, but whether consistency differs |
| 19 | [One-Sample T-Statistic](t_test_one_sample.md) | Intermediate | This tests whether your sample's average differs from a claimed value |
| 20 | [Two-Sample T-Statistic](t_test_two_sample.md) | Intermediate | Compares the averages of two groups and returns a t-statistic - near 0 means the groups are indistinguishable, large means one is genuinely higher or lower than the other |
| 21 | [Tracking Signal Threshold Check](tracking_signal_threshold.md) | Beginner | A tracking signal watches whether your forecast is persistently too high or too low |
| 22 | [Bias (Mean Error)](bias.md) | Beginner | Bias is the average of (actual minus forecast) |
| 23 | [MAE (Mean Absolute Error)](mae.md) | Beginner | MAE is the average miss, ignoring direction: forecast 110 when actual was 100 counts as 10, whether high or low |
| 24 | [MSE (Mean Squared Error)](mse.md) | Intermediate | MSE squares each error before averaging, which punishes big misses much harder than small ones |
| 25 | [RMSE (Root Mean Squared Error)](rmse.md) | Intermediate | RMSE is the square root of MSE |
| 26 | [MAPE (Mean Absolute Percentage Error)](mape.md) | Beginner | MAPE expresses error as a percentage of actual sales, so it works across products of different sizes |
| 27 | [SMAPE (Symmetric MAPE)](smape.md) | Intermediate | SMAPE divides the error by the average of actual and forecast instead of just the actual |
| 28 | [MPE (Mean Percentage Error)](mean_percentage_error.md) | Intermediate | MPE is like MAPE but keeps the sign, so it shows systematic percentage-level tilt: positive means under-forecasting in percent terms, negative means over-forecasting |
| 29 | [Percent Bias (PBIAS)](percent_bias.md) | Intermediate | PBIAS sums ALL errors and divides by the sum of all actuals, giving one overall percentage tilt |
| 30 | [MASE (Mean Absolute Scaled Error)](mase.md) | Advanced | MASE compares your forecast against the naive 'copy yesterday' forecast |
| 31 | [Forecast Value Added (FVA)](forecast_value_added.md) | Intermediate | FVA measures whether your whole forecasting process (with its meetings, judgments, and overrides) actually beats a naive baseline |
| 32 | [Diebold-Mariano Test](diebold_mariano_test.md) | Advanced | Two forecasts, one winner - but is the win real or luck? The DM test compares their errors and returns a statistic: far from 0 means one forecast is genuinely better, near 0 means the difference is noise |
| 33 | [Anderson-Darling Statistic](anderson_darling_test.md) | Advanced | Checks whether your data plausibly follows a bell-curve (normal) shape, paying special attention to the tails |
| 34 | [Shapiro-Wilk Approximation](shapiro_wilk_approx.md) | Advanced | Another bell-curve check, famous for being sensitive even with small samples |
| 35 | [Jarque-Bera Statistic](jarque_bera_test.md) | Advanced | A shape test built from skewness (lean) and kurtosis (shockiness) together |
| 36 | [Chi-Square Goodness of Fit](chi_square_goodness_of_fit.md) | Intermediate | Compares observed counts against expected counts across categories |
| 37 | [Kolmogorov-Smirnov Test (One Sample)](kolmogorov_smirnov_test.md) | Advanced | KS compares the whole shape of your data to a reference pattern - it walks along the sorted values and measures the biggest gap between what you have and what you'd expect |
| 38 | [KS Test (Two Samples)](kolmogorov_smirnov_two_sample.md) | Advanced | Asks whether two batches of data come from the same overall pattern - not just the same average |
| 39 | [Mann-Whitney U](mann_whitney_u.md) | Advanced | A rank-based contest between two groups: pool all values, rank them, and see whether one group dominates the top ranks |
| 40 | [Wilcoxon Signed-Rank](wilcoxon_signed_rank.md) | Advanced | Tests paired before/after differences: rank the sizes of the changes and see whether positive or negative changes dominate |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_statistics.md](../../flashcards/flashcards_statistics.md)
- Recall drill: [drills/drill_statistics.md](../../drills/drill_statistics.md)
