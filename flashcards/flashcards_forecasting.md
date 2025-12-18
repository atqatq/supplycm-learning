---
title: "Flashcards: Forecasting | supplycm Learning"
description: "Spaced-repetition flashcards for all 50 supplycm forecasting algorithms."
keywords: "flashcards, forecasting, supply chain, recall"
---

# Flashcards: Forecasting

50 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `naive_forecast` do? | Naive Forecast: Copy the last actual value and use it as the next forecast. |
| 2 | What does `seasonal_naive_forecast` do? | Seasonal Naive Forecast: The naive method with a memory: forecast next period with the value from the SAME season last cycle. |
| 3 | What does `average_method` do? | Average Method: Forecast every future period with the average of ALL history. |
| 4 | What does `simple_moving_average` do? | Simple Moving Average (SMA): Average the last N periods and use that as the forecast - then slide the window forward. |
| 5 | What does `weighted_moving_average` do? | Weighted Moving Average: A moving average with opinions: give recent periods bigger weights (0.5, 0.3, 0.2) so yesterday matters more than last week. |
| 6 | What does `rolling_mean_forecast` do? | Rolling Mean Forecast: Like the moving average, but built for rolling forward: it computes the mean of the last window and projects it across a forecast horizon. |
| 7 | What does `moving_median_filter` do? | Moving Median Filter: The moving average's tougher sibling: take the MEDIAN (middle value) of the last N points instead of the mean. |
| 8 | What does `drift_method` do? | Drift Method: The naive forecast plus a trend: measure the average change per period over all history (the drift), then extend that slope into the future. |
| 9 | What does `single_exponential_smoothing` do? | Single Exponential Smoothing (SES): The workhorse level forecaster: each new estimate blends the latest actual with the previous estimate - alpha says how much each gets. |
| 10 | What does `ses_with_drift` do? | SES with Drift: SES handles level; this adds a slow trend estimate on top. |
| 11 | What does `holt_linear_trend` do? | Holt's Linear Trend: Holt runs TWO smoothing engines at once: alpha tracks the level, beta tracks the trend. |
| 12 | What does `dampened_trend` do? | Dampened Trend Method: Holt with brakes: a damping factor (phi) shrinks the trend each period forward - +10, then +9.5, then +9. |
| 13 | What does `holt_winters` do? | Holt-Winters (Triple Smoothing): Three engines in one: level (alpha), trend (beta), and season (gamma) - smoothed together and projected forward. |
| 14 | What does `doubling_seasonal_smoothing` do? | Doubling Seasonal Smoothing: An experimental variant that lets the seasonal pattern ADAPT at two time scales - capturing patterns that slowly shift or double in length. |
| 15 | What does `classical_decomposition` do? | Classical Decomposition: Split history into its three ingredients: trend (the slow drift), seasonal (the repeating wiggle), and residual (whatever is left). |
| 16 | What does `mstl_decomposition` do? | MSTL Decomposition (Multiple Seasons): Real series often have MORE than one season: hourly data has daily AND weekly rhythms. |
| 17 | What does `seasonal_trend_loess` do? | STL (Seasonal-Trend Loess): STL is the artisan version of decomposition: it fits trend and season with local, flexible smoothing (LOESS) instead of rigid averages. |
| 18 | What does `seasonal_indices` do? | Seasonal Indices: Boils the repeating pattern into one number per season position: 1.0 is average, 1.3 means 30% above typical, 0.7 means 30% below. |
| 19 | What does `crostons_method` do? | Croston's Method: For intermittent demand - mostly zeros with occasional sales - Croston tracks TWO things separately: how BIG a sale is when it happens, and how LONG between sales. |
| 20 | What does `croston_with_decay` do? | Croston with Decay: Croston with a twist for fading products: a decay factor progressively shrinks the forecast when sales keep not happening. |
| 21 | What does `sba_method` do? | SBA (Syntetos-Boylan Approximation): Croston's method quietly OVER-forecasts intermittent demand by about the interval size. |
| 22 | What does `tsb_method` do? | TSB Method: TSB (Teunter-Syntetos-Babai) fixes Croston's blind spot for DEMAND LOSS: it tracks the probability that a period has ANY sale, and the size when it does. |
| 23 | What does `pegels_classification` do? | Pegels Classification: Before choosing an exponential smoothing model, CLASSIFY your data: does it have error structure, trend, season? Pegels returns a compact code like 'ANN' (no trend, no season) or 'AAM' (additive trend, multiplicative season) - the map that picks the right smoothing engine for you. |
| 24 | What does `linear_regression_forecast` do? | Linear Regression Forecast: Fits the best straight line through your history and extends it: one slope, one intercept, honest and explainable. |
| 25 | What does `polynomial_regression_forecast` do? | Polynomial Regression Forecast: A flexible curve instead of a straight line - it can bend with accelerating or decelerating growth. |
| 26 | What does `exponential_trend_forecast` do? | Exponential Trend Forecast: For growth that COMPOUNDS - each period grows by a percentage, not a fixed amount. |
| 27 | What does `gompertz_trend` do? | Gompertz Curve: The S-curve of adoption: slow start, rapid middle growth, then flattening at a ceiling. |
| 28 | What does `logistic_trend` do? | Logistic Curve: The Gompertz's symmetrical sibling: an S-curve that rises slowly, speeds through the middle, and decelerates symmetrically toward its ceiling. |
| 29 | What does `browns_double_exponential` do? | Brown's Double Exponential Smoothing: Holt's trend tracking with a clever trick: smooth the series TWICE, and estimate the trend from the GAP between the two smoothings. |
| 30 | What does `browns_triple_exponential` do? | Brown's Triple Exponential Smoothing: The same idea one level deeper: smooth THREE times, and the two gaps between the three smoothings jointly reveal both trend and curvature. |
| 31 | What does `theta_method` do? | Theta Method: A deceptively simple trick that wins forecasting competitions: split the series into two 'theta lines' - one exaggerating the long-term curve, one emphasizing short-term movement - combine their information, and extrapolate. |
| 32 | What does `ar_model` do? | AR Model (Autoregressive): An AR model forecasts tomorrow as a weighted recipe of recent history: 'tomorrow = 0.5 x today + 0.3 x yesterday + base'. |
| 33 | What does `ma_model` do? | MA Model (Moving Average Process): Not the moving-average FORECAST - the statistical MA model: today's value = base level plus weighted recent SHOCKS (surprises). |
| 34 | What does `var_model` do? | VAR Model (Vector Autoregression): Two (or more) series that move each OTHER - like price and volume, or two linked products - deserve a model that captures the feedback. |
| 35 | What does `autocorrelation` do? | Autocorrelation (ACF): How strongly does the series correlate with ITSELF, shifted by 1, 2, 3. |
| 36 | What does `partial_autocorrelation` do? | Partial Autocorrelation (PACF): PACF asks the sharper question: after accounting for shorter lags, does THIS lag still add explanatory power? Lag-3 correlation might just be lag-1 echoing; PACF strips the echoes and shows the true direct connections - the blueprint for choosing model order. |
| 37 | What does `ljung_box_test` do? | Ljung-Box Test Statistic: After fitting a model, the LEFTOVERS (residuals) should be boring - no pattern left. |
| 38 | What does `adf_test` do? | ADF Test Statistic (Stationarity): Many models assume the series is STATIONARY - same average behavior over time. |
| 39 | What does `kpss_test` do? | KPSS Test Statistic (Stationarity): The ADF's mirror image: KPSS assumes stationarity and looks for evidence AGAINST it. |
| 40 | What does `hurst_exponent` do? | Hurst Exponent: One number that describes a series' soul: near 0.5 means a random walk (no memory), above 0.5 means persistence (trends continue), below 0.5 means anti-persistence (moves reverse). |
| 41 | What does `theils_u` do? | Theil's U: A fairness ratio: your forecast's error divided by the naive forecast's error. |
| 42 | What does `box_cox_transform` do? | Box-Cox Transform: Some series wobble MORE as they grow - multiplicative noise. |
| 43 | What does `inverse_box_cox` do? | Inverse Box-Cox Transform: The way home: after modeling on the transformed scale, this restores forecasts to real units. |
| 44 | What does `akaike_information_criterion` do? | AIC (Akaike Information Criterion): AIC scores models on a honest curve: fit quality minus a penalty for each parameter. |
| 45 | What does `bayesian_information_criterion` do? | BIC (Bayesian Information Criterion): AIC's stricter sibling: same idea - fit minus complexity penalty - but the penalty grows with sample size. |
| 46 | What does `bates_granger_combination` do? | Bates-Granger Forecast Combination: Two forecasts, each wrong differently - averaging them (weighted by inverse error) often beats either one. |
| 47 | What does `top_down_reconciliation` do? | Top-Down Reconciliation: You have one solid national forecast and messy product-level detail. |
| 48 | What does `bottom_up_reconciliation` do? | Bottom-Up Reconciliation: The opposite route: trust the detailed forecasts and SUM them upward. |
| 49 | What does `tracking_signal` do? | Tracking Signal: A forecast alarm system: it accumulates forecast errors and divides by their typical size. |
| 50 | What does `brier_score` do? | Brier Score: Scores PROBABILITY forecasts: you said 80% chance of a stockout and it happened (or didn't) - the Brier score grades the calibration of such statements over many cases. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
