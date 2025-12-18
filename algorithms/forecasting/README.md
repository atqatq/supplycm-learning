---
title: "Forecasting Algorithms | supplycm Algorithm Library"
description: "All 50 forecasting algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, forecasting, forecasting, supply chain algorithms"
---

# Forecasting (50 algorithms)

Predict next week's, next month's, next quarter's demand.

**Levels:** 7 beginner · 20 intermediate · 23 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Naive Forecast](naive_forecast.md) | Beginner | Copy the last actual value and use it as the next forecast |
| 2 | [Seasonal Naive Forecast](seasonal_naive_forecast.md) | Beginner | The naive method with a memory: forecast next period with the value from the SAME season last cycle |
| 3 | [Average Method](average_method.md) | Beginner | Forecast every future period with the average of ALL history |
| 4 | [Simple Moving Average (SMA)](simple_moving_average.md) | Beginner | Average the last N periods and use that as the forecast - then slide the window forward |
| 5 | [Weighted Moving Average](weighted_moving_average.md) | Intermediate | A moving average with opinions: give recent periods bigger weights (0.5, 0.3, 0.2) so yesterday matters more than last week |
| 6 | [Rolling Mean Forecast](rolling_mean_forecast.md) | Beginner | Like the moving average, but built for rolling forward: it computes the mean of the last window and projects it across a forecast horizon |
| 7 | [Moving Median Filter](moving_median_filter.md) | Intermediate | The moving average's tougher sibling: take the MEDIAN (middle value) of the last N points instead of the mean |
| 8 | [Drift Method](drift_method.md) | Intermediate | The naive forecast plus a trend: measure the average change per period over all history (the drift), then extend that slope into the future |
| 9 | [Single Exponential Smoothing (SES)](single_exponential_smoothing.md) | Beginner | The workhorse level forecaster: each new estimate blends the latest actual with the previous estimate - alpha says how much each gets |
| 10 | [SES with Drift](ses_with_drift.md) | Intermediate | SES handles level; this adds a slow trend estimate on top |
| 11 | [Holt's Linear Trend](holt_linear_trend.md) | Intermediate | Holt runs TWO smoothing engines at once: alpha tracks the level, beta tracks the trend |
| 12 | [Dampened Trend Method](dampened_trend.md) | Intermediate | Holt with brakes: a damping factor (phi) shrinks the trend each period forward - +10, then +9.5, then +9 |
| 13 | [Holt-Winters (Triple Smoothing)](holt_winters.md) | Intermediate | Three engines in one: level (alpha), trend (beta), and season (gamma) - smoothed together and projected forward |
| 14 | [Doubling Seasonal Smoothing](doubling_seasonal_smoothing.md) | Advanced | An experimental variant that lets the seasonal pattern ADAPT at two time scales - capturing patterns that slowly shift or double in length |
| 15 | [Classical Decomposition](classical_decomposition.md) | Intermediate | Split history into its three ingredients: trend (the slow drift), seasonal (the repeating wiggle), and residual (whatever is left) |
| 16 | [MSTL Decomposition (Multiple Seasons)](mstl_decomposition.md) | Advanced | Real series often have MORE than one season: hourly data has daily AND weekly rhythms |
| 17 | [STL (Seasonal-Trend Loess)](seasonal_trend_loess.md) | Advanced | STL is the artisan version of decomposition: it fits trend and season with local, flexible smoothing (LOESS) instead of rigid averages |
| 18 | [Seasonal Indices](seasonal_indices.md) | Beginner | Boils the repeating pattern into one number per season position: 1.0 is average, 1.3 means 30% above typical, 0.7 means 30% below |
| 19 | [Croston's Method](crostons_method.md) | Intermediate | For intermittent demand - mostly zeros with occasional sales - Croston tracks TWO things separately: how BIG a sale is when it happens, and how LONG between sales |
| 20 | [Croston with Decay](croston_with_decay.md) | Advanced | Croston with a twist for fading products: a decay factor progressively shrinks the forecast when sales keep not happening |
| 21 | [SBA (Syntetos-Boylan Approximation)](sba_method.md) | Intermediate | Croston's method quietly OVER-forecasts intermittent demand by about the interval size |
| 22 | [TSB Method](tsb_method.md) | Advanced | TSB (Teunter-Syntetos-Babai) fixes Croston's blind spot for DEMAND LOSS: it tracks the probability that a period has ANY sale, and the size when it does |
| 23 | [Pegels Classification](pegels_classification.md) | Intermediate | Before choosing an exponential smoothing model, CLASSIFY your data: does it have error structure, trend, season? Pegels returns a compact code like 'ANN' (no trend, no season) or 'AAM' (additive trend, multiplicative season) - the map that picks the right smoothing engine for you |
| 24 | [Linear Regression Forecast](linear_regression_forecast.md) | Intermediate | Fits the best straight line through your history and extends it: one slope, one intercept, honest and explainable |
| 25 | [Polynomial Regression Forecast](polynomial_regression_forecast.md) | Advanced | A flexible curve instead of a straight line - it can bend with accelerating or decelerating growth |
| 26 | [Exponential Trend Forecast](exponential_trend_forecast.md) | Intermediate | For growth that COMPOUNDS - each period grows by a percentage, not a fixed amount |
| 27 | [Gompertz Curve](gompertz_trend.md) | Advanced | The S-curve of adoption: slow start, rapid middle growth, then flattening at a ceiling |
| 28 | [Logistic Curve](logistic_trend.md) | Advanced | The Gompertz's symmetrical sibling: an S-curve that rises slowly, speeds through the middle, and decelerates symmetrically toward its ceiling |
| 29 | [Brown's Double Exponential Smoothing](browns_double_exponential.md) | Intermediate | Holt's trend tracking with a clever trick: smooth the series TWICE, and estimate the trend from the GAP between the two smoothings |
| 30 | [Brown's Triple Exponential Smoothing](browns_triple_exponential.md) | Advanced | The same idea one level deeper: smooth THREE times, and the two gaps between the three smoothings jointly reveal both trend and curvature |
| 31 | [Theta Method](theta_method.md) | Intermediate | A deceptively simple trick that wins forecasting competitions: split the series into two 'theta lines' - one exaggerating the long-term curve, one emphasizing short-term movement - combine their information, and extrapolate |
| 32 | [AR Model (Autoregressive)](ar_model.md) | Advanced | An AR model forecasts tomorrow as a weighted recipe of recent history: 'tomorrow = 0.5 x today + 0.3 x yesterday + base' |
| 33 | [MA Model (Moving Average Process)](ma_model.md) | Advanced | Not the moving-average FORECAST - the statistical MA model: today's value = base level plus weighted recent SHOCKS (surprises) |
| 34 | [VAR Model (Vector Autoregression)](var_model.md) | Advanced | Two (or more) series that move each OTHER - like price and volume, or two linked products - deserve a model that captures the feedback |
| 35 | [Autocorrelation (ACF)](autocorrelation.md) | Intermediate | How strongly does the series correlate with ITSELF, shifted by 1, 2, 3 |
| 36 | [Partial Autocorrelation (PACF)](partial_autocorrelation.md) | Advanced | PACF asks the sharper question: after accounting for shorter lags, does THIS lag still add explanatory power? Lag-3 correlation might just be lag-1 echoing; PACF strips the echoes and shows the true direct connections - the blueprint for choosing model order |
| 37 | [Ljung-Box Test Statistic](ljung_box_test.md) | Advanced | After fitting a model, the LEFTOVERS (residuals) should be boring - no pattern left |
| 38 | [ADF Test Statistic (Stationarity)](adf_test.md) | Advanced | Many models assume the series is STATIONARY - same average behavior over time |
| 39 | [KPSS Test Statistic (Stationarity)](kpss_test.md) | Advanced | The ADF's mirror image: KPSS assumes stationarity and looks for evidence AGAINST it |
| 40 | [Hurst Exponent](hurst_exponent.md) | Advanced | One number that describes a series' soul: near 0.5 means a random walk (no memory), above 0.5 means persistence (trends continue), below 0.5 means anti-persistence (moves reverse) |
| 41 | [Theil's U](theils_u.md) | Intermediate | A fairness ratio: your forecast's error divided by the naive forecast's error |
| 42 | [Box-Cox Transform](box_cox_transform.md) | Advanced | Some series wobble MORE as they grow - multiplicative noise |
| 43 | [Inverse Box-Cox Transform](inverse_box_cox.md) | Advanced | The way home: after modeling on the transformed scale, this restores forecasts to real units |
| 44 | [AIC (Akaike Information Criterion)](akaike_information_criterion.md) | Advanced | AIC scores models on a honest curve: fit quality minus a penalty for each parameter |
| 45 | [BIC (Bayesian Information Criterion)](bayesian_information_criterion.md) | Advanced | AIC's stricter sibling: same idea - fit minus complexity penalty - but the penalty grows with sample size |
| 46 | [Bates-Granger Forecast Combination](bates_granger_combination.md) | Advanced | Two forecasts, each wrong differently - averaging them (weighted by inverse error) often beats either one |
| 47 | [Top-Down Reconciliation](top_down_reconciliation.md) | Intermediate | You have one solid national forecast and messy product-level detail |
| 48 | [Bottom-Up Reconciliation](bottom_up_reconciliation.md) | Intermediate | The opposite route: trust the detailed forecasts and SUM them upward |
| 49 | [Tracking Signal](tracking_signal.md) | Intermediate | A forecast alarm system: it accumulates forecast errors and divides by their typical size |
| 50 | [Brier Score](brier_score.md) | Advanced | Scores PROBABILITY forecasts: you said 80% chance of a stockout and it happened (or didn't) - the Brier score grades the calibration of such statements over many cases |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_forecasting.md](../../flashcards/flashcards_forecasting.md)
- Recall drill: [drills/drill_forecasting.md](../../drills/drill_forecasting.md)
