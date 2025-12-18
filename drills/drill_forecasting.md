---
title: "Recall Drill: Forecasting | supplycm Learning"
description: "Active-recall drill with answer key covering all 50 supplycm forecasting algorithms."
keywords: "drill, recall, forecasting, supply chain practice"
---

# Recall Drill: Forecasting

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Naive Forecast** (`naive_forecast`)

1. What is the naive forecast for tomorrow?
2. Why keep a method this simple around?
3. When does naive fail hardest?

**Seasonal Naive Forecast** (`seasonal_naive_forecast`)

4. How does it differ from plain naive?
5. What breaks it?
6. Why is it the right baseline for seasonal items?

**Average Method** (`average_method`)

7. When does the average method beat naive?
8. Why does it fail on trends?
9. What does 'flat forever' imply about its assumptions?

**Simple Moving Average (SMA)** (`simple_moving_average`)

10. Window 3 vs window 12 - what changes?
11. Why do early slots come up empty?
12. How does SMA lag a rising trend?

**Weighted Moving Average** (`weighted_moving_average`)

13. What must the weights sum to?
14. Weighted vs simple MA - when bother?
15. How is this related to exponential smoothing?

**Rolling Mean Forecast** (`rolling_mean_forecast`)

16. What happens to the forecast if one crazy value enters the window?
17. Why do all horizon periods get the same number?
18. When would you extend the window before forecasting?

**Moving Median Filter** (`moving_median_filter`)

19. Why is the median robust to outliers?
20. Median vs mean on clean data - any difference?
21. What does a large window cost here?

**Drift Method** (`drift_method`)

22. How is drift computed?
23. What happens if the early history was atypical?
24. When does drift beat a fitted regression line?

**Single Exponential Smoothing (SES)** (`single_exponential_smoothing`)

25. Alpha 0.2 vs 0.8 - personalities?
26. Why 'exponential'?
27. When is SES the WRONG tool?

**SES with Drift** (`ses_with_drift`)

28. What does drift add over plain SES?
29. Why keep alpha moderate here?
30. When would you step up to Holt?

**Holt's Linear Trend** (`holt_linear_trend`)

31. What do alpha and beta control separately?
32. Beta too high - symptom?
33. Why damp the trend for long horizons?

**Dampened Trend Method** (`dampened_trend`)

34. What does phi = 0.9 vs 0.5 change?
35. Why is damping so often the right call?
36. Phi = 1 recovers what?

**Holt-Winters (Triple Smoothing)** (`holt_winters`)

37. What do the three smoothing parameters tune?
38. Additive vs multiplicative seasonality - when each?
39. How much history does it need?

**Doubling Seasonal Smoothing** (`doubling_seasonal_smoothing`)

40. When would a fixed season_length be wrong?
41. What is the practical risk of adaptive seasonality?
42. How would you validate it before trusting forecasts?

**Classical Decomposition** (`classical_decomposition`)

43. What belongs in the residual component?
44. Additive vs multiplicative decomposition - how to choose?
45. Decomposition vs Holt-Winters - relationship?

**MSTL Decomposition (Multiple Seasons)** (`mstl_decomposition`)

46. When do multiple seasonalities coexist?
47. What breaks classical decomposition that MSTL handles?
48. How do you choose the seasonal periods?

**STL (Seasonal-Trend Loess)** (`seasonal_trend_loess`)

49. What does 'local smoothing' (LOESS) actually do?
50. When is STL worth it over classical decomposition?
51. What does STL NOT give you?

**Seasonal Indices** (`seasonal_indices`)

52. What should the four indices average out to?
53. How do you deseasonalize a series?
54. One crazy December skews the December index. Fix?

**Croston's Method** (`crostons_method`)

55. Why do standard methods fail on intermittent demand?
56. What are the two tracked components?
57. When does Croston struggle?

**Croston with Decay** (`croston_with_decay`)

58. What does the decay factor control?
59. Why does plain Croston over-forecast dying products?
60. What's the danger of too much decay?

**SBA (Syntetos-Boylan Approximation)** (`sba_method`)

61. What bias does Croston have?
62. How big is SBA's correction?
63. Why do stock policies care so much about this bias?

**TSB Method** (`tsb_method`)

64. What does TSB track that Croston doesn't?
65. When does TSB beat SBA?
66. What do alpha and beta mean here?

**Pegels Classification** (`pegels_classification`)

67. What do the three letters describe?
68. Series classified 'AAN' - which method fits?
69. Why classify at all instead of always using Holt-Winters?

**Linear Regression Forecast** (`linear_regression_forecast`)

70. What do slope and intercept mean in business words?
71. When does a straight line lie?
72. How far would you trust a linear extrapolation?

**Polynomial Regression Forecast** (`polynomial_regression_forecast`)

73. Why do high-degree polynomials explode?
74. Degree 2 vs degree 5 - which would you defend?
75. How is this different from exponential trend fitting?

**Exponential Trend Forecast** (`exponential_trend_forecast`)

76. Linear +10 vs exponential +10% - when do they diverge?
77. Why do exponential extrapolations embarrass forecasters?
78. What's the honest way to use it?

**Gompertz Curve** (`gompertz_trend`)

79. What are the three phases of a Gompertz curve?
80. Why does the ceiling matter to planners?
81. When does fitting fail?

**Logistic Curve** (`logistic_trend`)

82. Logistic vs Gompertz - what differs?
83. What business insight hides in the midpoint?
84. Why do forecasters love S-curves?

**Brown's Double Exponential Smoothing** (`browns_double_exponential`)

85. How does the trend hide in double smoothing?
86. One parameter vs Holt's two - trade-off?
87. When would you step up to Holt?

**Brown's Triple Exponential Smoothing** (`browns_triple_exponential`)

88. What does the third smoothing add?
89. Why keep alpha LOW here?
90. Relationship to Holt-Winters?

**Theta Method** (`theta_method`)

91. What does theta = 2 do?
92. Why does such a simple method perform so well?
93. When would you NOT use it?

**AR Model (Autoregressive)** (`ar_model`)

94. What does an AR coefficient of 1 vs 0 imply?
95. Why fit AR when SES exists?
96. What breaks AR models?

**MA Model (Moving Average Process)** (`ma_model`)

97. What is a 'shock' in MA language?
98. MA model vs moving-average forecast - totally different?
99. What does a large MA coefficient mean operationally?

**VAR Model (Vector Autoregression)** (`var_model`)

100. When does VAR beat two separate AR models?
101. What does a near-zero cross coefficient mean?
102. What's the data appetite for VAR?

**Autocorrelation (ACF)** (`autocorrelation`)

103. What does a high lag-1 autocorrelation mean?
104. How does ACF reveal season length?
105. ACF fades slowly with no spikes - diagnosis?

**Partial Autocorrelation (PACF)** (`partial_autocorrelation`)

106. PACF vs ACF - what does 'partial' remove?
107. A lag-4 ACF spike but no lag-4 PACF - interpretation?
108. How does PACF guide AR model building?

**Ljung-Box Test Statistic** (`ljung_box_test`)

109. What do 'clean' residuals look like statistically?
110. Ljung-Box flags my model. First response?
111. Can a model pass Ljung-Box and still forecast badly?

**ADF Test Statistic (Stationarity)** (`adf_test`)

112. What is a 'unit root' in plain words?
113. Series fails ADF. Standard fix?
114. Why does stationarity matter to forecasters?

**KPSS Test Statistic (Stationarity)** (`kpss_test`)

115. How do ADF and KPSS hypotheses differ?
116. Both tests agree the series is non-stationary. Action?
117. They disagree. Now what?

**Hurst Exponent** (`hurst_exponent`)

118. Hurst near 0.7 - what forecasting attitude fits?
119. Hurst near 0.3 - opposite attitude?
120. Why is 0.5 the neutral point?

**Theil's U** (`theils_u`)

121. U = 1.1 - verdict?
122. Why compare against naive specifically?
123. Can a great MAPE hide a bad U?

**Box-Cox Transform** (`box_cox_transform`)

124. What does lambda = 0 mean?
125. Why transform at all if we inverse later?
126. How do you get real units back?

**Inverse Box-Cox Transform** (`inverse_box_cox`)

127. What happens if you forget the inverse step?
128. Why must lambda match between transform and inverse?
129. Where do prediction INTERVALS get transformed?

**AIC (Akaike Information Criterion)** (`akaike_information_criterion`)

130. What does AIC penalize?
131. AIC vs BIC - whose penalty is harsher?
132. Is an AIC of 42 'good'?

**BIC (Bayesian Information Criterion)** (`bayesian_information_criterion`)

133. When do AIC and BIC pick different winners?
134. Which should guide SKU-level automated selection?
135. What does BIC's data-growing penalty imply?

**Bates-Granger Forecast Combination** (`bates_granger_combination`)

136. Why does combining beat picking one winner?
137. When does combining FAIL to help?
138. How is this different from just averaging 50/50?

**Top-Down Reconciliation** (`top_down_reconciliation`)

139. What's the core trade-off vs bottom-up?
140. When do proportions mislead?
141. How often should proportions refresh?

**Bottom-Up Reconciliation** (`bottom_up_reconciliation`)

142. What does bottom-up preserve that top-down destroys?
143. Why can the bottom-up total be less accurate than its parts?
144. What's the middle path?

**Tracking Signal** (`tracking_signal`)

145. What does a signal of +5 mean?
146. Why divide cumulative error by mean absolute error?
147. Signal crosses the threshold. First move?

**Brier Score** (`brier_score`)

148. What kind of forecast does Brier grade?
149. Saying 50% for everything scores what?
150. Why should planners care about calibration?

Total: 150 questions.

## Part 2 - Answer key

1. Today's actual value - copied forward unchanged.
2. It is the fairness benchmark: if your elaborate model can't beat it, the model isn't earning its complexity.
3. Trends and seasonality - it always lags one step behind any pattern.
4. It copies from one season AGO, not one period ago - preserving the pattern naive destroys.
5. Trends (last year's level is stale) and shifting seasonality - the calendar repeats, the world doesn't always.
6. Because comparing a seasonal model against plain naive is a rigged game - the seasonal baseline is the honest opponent.
7. When data is noisy but stable - averaging damps the noise naive would copy.
8. It anchors on the historical middle while the world has moved - forecasts are systematically stale.
9. No trend, no seasonality, constant level - state those assumptions out loud before trusting it.
10. 3 reacts quickly with jitter; 12 is smooth but slow to notice real shifts.
11. A full window of history does not exist yet - honesty about what the average could know.
12. It averages past values including lower ones, so it sits below the current level - always trailing.
13. 1.0 - so the forecast stays on the data's scale instead of inflating or shrinking.
14. When recent periods genuinely carry more information - the weights encode that belief explicitly.
15. Exponential smoothing is the infinite version: weights that decay forever by a constant factor.
16. It contaminates all horizon periods until the window slides past - a known cost of simple averaging.
17. The method projects a LEVEL, not a trend - flat futures are its honest opinion.
18. When noise is high and you value stability over responsiveness.
19. It depends on the middle ORDER, not the magnitude - one extreme value cannot pull it.
20. Barely - on well-behaved data they nearly agree; on spiky data they diverge dramatically.
21. Responsiveness - the median vote grows sluggish as the window widens.
22. Total change (last minus first) divided by the number of steps - the average slope of the whole history.
23. The slope distorts - drift anchors on the endpoints, so outliers at either end steer everything.
24. Often never exactly - but with 2 data points of computation it gets remarkably close on clean trends.
25. 0.2 is calm and laggy; 0.8 is nervous and reactive - choose by how fast the world actually changes.
26. Weights on older data shrink by a constant factor each step - an exponential decay of memory.
27. Clear trends (it lags) or seasons (it ignores) - upgrade to Holt or Holt-Winters then.
28. Direction - the forecast stops pretending the world is flat when it plainly slopes.
29. A jumpy level plus a jumpy drift compounds noise - moderation keeps both stable.
30. When the trend itself is strong and persistent - Holt's beta tracks it explicitly.
31. Alpha: how fast the level adapts; beta: how fast the trend estimate adapts.
32. The trend estimate whipsaws with every noise blip, making forecasts seasick.
33. Real trends rarely run forever - undamped Holt shoots to absurd futures within a few periods.
34. 0.9 lets the trend run longer; 0.5 kills it fast - the dial from Holt to near-SES.
35. Untamed trends over-forecast dramatically at longer horizons; damping costs little when trends persist and saves a lot when they fade.
36. Plain Holt - no damping at all.
37. Alpha: level speed; beta: trend speed; gamma: how quickly seasonal factors update.
38. Additive: spikes are a constant size (+20 every summer). Multiplicative: spikes scale with level (x1.5) - use multiplicative when seasons grow with the business.
39. At least two full seasons to learn a pattern and verify it repeats.
40. Calendar drift, growing cycles, or data aggregated oddly - the true cycle no longer matches the assumed one.
41. Overfitting odd history - it can 'learn' patterns that were noise.
42. Hold out recent periods, compare against fixed-length Holt-Winters, and inspect the seasonal components for sanity.
43. Everything unexplained: noise, promotions, one-off events - big residuals scream for investigation.
44. Additive if seasonal swings stay constant-sized; multiplicative if they scale with the level (bigger business, bigger swings).
45. Same three ingredients; decomposition explains them for diagnosis, Holt-Winters smooths and projects them for forecasting.
46. High-frequency operations: daily pattern within weekly pattern within yearly pattern - each calendar leaves its fingerprint.
47. Classical handles ONE season length; layered cycles contaminate its single seasonal estimate.
48. From the data's clock: 24 and 168 for hourly (day/week), 7 and 365 for daily - use the cycles your business actually repeats.
49. Fits small flexible curves over local neighborhoods - capturing bends and drifts rigid methods must average away.
50. When the pattern evolves, the trend bends, or outliers plague the data - flexibility earns its keep.
51. A forecast by itself - it explains structure; pair it with forecasting the extracted components.
52. About 1.0 - they are shares of the average period, and shares must balance.
53. Divide each actual by its position's index - what remains shows the true trend without the wiggle.
54. Compute indices over multiple years, or cap/dampen the outlier's influence before averaging.
55. They average the zeros in, forecasting sizes like 1.2 every period - a number that is simultaneously too big for quiet days and too small for sale days.
56. Demand size when a sale occurs, and the interval between sales - the forecast divides one by the other.
57. When demand shifts (level or frequency changes) - its slow smoothing lags regime changes.
58. How fast expectations shrink during sales droughts - 0.95 drifts down gently, 0.8 gives up quickly.
59. It anchors on the historical average size and interval, blind to the fact that demand is leaving.
60. Killing forecasts for parts that come back - a big dormant contract sale would look 'dead' right before it returns.
61. It forecasts the size/interval ratio, which overstates average demand per period by roughly the interval's worth.
62. The forecast shrinks by a factor tied to alpha - at typical alphas, roughly 10-15% lower than Croston.
63. Safety stock and order quantities multiply the forecast - a 12% level bias becomes a 12% inventory bias, item after item.
64. The PROBABILITY of demand occurring each period - intervals become probabilities, and silence moves them.
65. When demand genuinely disappears or returns - SBA assumes intervals are stable; TSB lets the demand rate itself shift.
66. Alpha updates the demand probability on each period's outcome; beta updates the size estimate when demand happens.
67. Error type, trend type, season type - each 'A' (additive), 'M' (multiplicative), or 'N' (none).
68. Holt's linear trend - additive trend, no seasonality.
69. Fit without structure is noise-fitting - simpler matched models are more stable and just as accurate.
70. Slope: change per period; intercept: the line's starting point - together they say 'from here, growing this fast'.
71. When growth curves, saturates, or seasons - the line happily extrapolates nonsense beyond its evidence.
72. A few periods - and never past a known ceiling or turning point you can name.
73. They gain a wobble for every extra degree - outside the data range, those wobbles amplify into absurd values.
74. 2 - a gentle bend is usually real physics (growth, saturation); degree 5 is usually the data's biography, not its future.
75. Polynomial bends by arithmetic; exponential compounds by percentage - the mechanics of growth differ.
76. Quickly! At level 500, linear adds 10 but exponential adds 50 - the curves split within a few periods.
77. Nothing compounds forever - markets saturate; the model doesn't know that unless you tell it.
78. Short horizons while growth is real, with a documented story for when the compounding stops.
79. Slow early adoption, rapid growth, saturation near the ceiling - the full life story of many products.
80. Capacity, inventory, and growth budgets must stop assuming the middle phase lasts forever.
81. If history only covers ONE phase - the model guesses the rest; early-stage fits are acts of faith.
82. Symmetry: logistic decelerates symmetrically; Gompertz is skewed. Fit both and let the data pick.
83. The midpoint is peak growth speed - after it, every plan should assume slower gains.
84. Because adoption really does stop - curves that honor ceilings produce forecasts that age gracefully.
85. The second smoothing lags the first on trending data - the gap grows with the slope, so the gap IS the trend estimate.
86. Simplicity and robustness vs flexibility - Brown's can't weight level and trend adaptation separately.
87. When trend changes abruptly and one knob can't track both level and slope quickly enough.
88. Curvature awareness - two gaps instead of one, enough to estimate a bending (quadratic) trajectory.
89. Triple smoothing compounds reactivity - a high alpha triples down on noise; calm parameters keep the estimate stable.
90. Different lineage: Holt-Winters smooths components separately with three knobs; Brown's chains one knob through multiple passes - same goal, opposite philosophy.
91. It exaggerates the series' curvature in one decomposition line - amplifying the structure that plain lines average away.
92. It captures the two things business series actually have - gentle trend and recent level - without the flexibility to chase noise.
93. Strong multiplicative seasonality or intermittent demand - those need dedicated engines.
94. Near 1: momentum - yesterday persists (random-walk-like). Near 0: mean reversion - today's spike is noise, the average beckons.
95. AR tells you HOW the past propagates (coefficients you can inspect); SES just smooths without explaining.
96. Structural breaks - coefficients learned on the old regime misfire after the world changes.
97. The unexpected part of a period - actual minus what the base process predicted.
98. Yes - one is a statistical model of shock propagation; the other is a forecasting heuristic. Same words, different universes.
99. Surprises linger - a promotional spike keeps echoing; plan buffers accordingly.
100. When the series influence each other - ignoring the feedback loses real predictive signal.
101. No influence in that direction - the 'partnership' is really a solo act.
102. Hungry - two series means two coefficient sets per lag; short histories make noisy estimates.
103. Persistence: high days follow high days - momentum that smoothing methods can exploit.
104. Correlation peaks at the cycle distance - a lag-12 spike in monthly data whispers 'yearly'.
105. Trend or a random walk - the series needs differencing or trend handling before further modeling.
106. The influence of intermediate lags - it isolates each lag's DIRECT contribution.
107. The seasonal echo travels through nearer lags - the direct connection is weaker than ACF suggests.
108. Significant PACF lags are candidate orders - when PACF cuts off after lag 2, try AR(2) first.
109. No autocorrelation at any lag - pure noise; all signal extracted.
110. Look at WHICH lags correlate - missing season or insufficient lag order usually reveals itself there.
111. Yes - it certifies pattern capture, not accuracy; keep checking error metrics too.
112. The series' level wanders without a home - shocks accumulate forever instead of reverting.
113. Difference it (model the CHANGES) - most trending business series turn stationary after one difference.
114. Because models extrapolate patterns they assume are stable - non-stationary data breaks that promise.
115. Opposite nulls: ADF assumes non-stationarity (reject = stationary); KPSS assumes stationarity (reject = non-stationary).
116. Difference or detrend, then re-test - agreement makes the diagnosis credible.
117. Suspicion of borderline behavior - try both specifications, or use methods tolerant of mild non-stationarity.
118. Persistence - trend-following logic; the past direction carries real information.
119. Mean reversion - spikes tend to reverse; lean against recent moves instead of following them.
120. It matches a random walk - the past direction carries no information about the next move.
121. 11% worse than naive - drop the method or fix it; copying yesterday was better.
122. It is the zero-effort benchmark everyone understands - beating it is the minimum bar for any 'smart' method.
123. Yes - on easy-to-forecast series, naive also has great MAPE; U reveals whether YOUR method added anything.
124. The log transform - the classic choice for multiplicative, percentage-growing series.
125. Because models learn better on steady-variance data - the transform is scaffolding, removed once the structure is built.
126. The inverse Box-Cox - always forecast on the transformed scale, then convert results home.
127. You plan with log-scale numbers - quantities 100x too small or meaningless - a classic, costly pipeline bug.
128. They are one operation in two directions - mismatched lambda lands you in the wrong units entirely.
129. Through the same inverse - intervals that were symmetric up there come back asymmetric down here, honestly.
130. Every extra parameter - complexity must pay rent in genuine fit improvement or the score rises.
131. BIC's - it taxes complexity harder and favors simpler models, especially with lots of data.
132. Meaningless alone - AIC only compares models on the SAME data; lower-than-the-alternative is the entire grammar.
133. When a complex model fits somewhat better - AIC may accept it, BIC may reject the complexity as not worth it at that sample size.
134. BIC for stability and simplicity; AIC when small fit gains matter operationally.
135. As evidence accumulates, only genuinely useful complexity survives - big data makes the bar higher, not lower.
136. Errors that don't overlap cancel - the blend's mistakes are smaller than either ingredient's.
137. When forecasts are near-identical - no diversity, no cancellation, just the same error twice.
138. Weights adapt to demonstrated accuracy - the reliable model speaks louder; 50/50 trusts blindly.
139. Consistency and noise reduction vs detail accuracy - top-down guarantees the sum but flattens local signal.
140. When the mix is shifting - new products, regional growth differences - stale proportions bake old reality into new numbers.
141. Regularly, from recent actual mix - proportions are a policy choice with a shelf life.
142. SKU-level signal - real product stories survive the aggregation.
143. Unbiased errors ADD in aggregation - the total carries the sum of everyone's noise; top-down would have imposed calm.
144. Middle-out or optimized reconciliation - reconcile both directions with weights; modern tools blend instead of choosing.
145. Persistent under-forecasting - actuals exceeded forecasts repeatedly in the same direction.
146. To scale the alarm: +4 means 'bias of 4 typical errors' - comparable across items of any size.
147. Investigate causes (new customer? promo? price change?) before re-fitting - the signal detects bias, not its story.
148. Probabilities of yes/no events - not quantities: '70% chance of delay', not '70 units'.
149. 0.25 always - the safe-but-useless baseline; real calibration must beat it.
150. Because decisions price in probabilities - if '90% reliable supplier' actually delivers 70%, buffers are built on fiction.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
