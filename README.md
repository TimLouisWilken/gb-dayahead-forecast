# GB day-ahead power price forecast (live)

Automatically published every morning (~08:50 UK time, before EPEX/N2EX gate closure) by an
online-learning research pipeline:

- **Point forecast**: Bernstein Online Aggregation over 6 selected members
  (LSTM+RF correction, gradient boosting, Transformer, LEAR, merit-order regression, Chronos-Bolt),
  each retrained/updated daily on a strict 07:30 UTC D-1 information set (no look-ahead).
- **Quantiles**: Quantile Regression Averaging over the 6 selected members plus two dedicated
  GBM tail forecasts (QRA-8), centred on the point forecast and calibrated with adaptive
  conformal inference.
- **Benchmark**: realised daily MAE is published against the standard naive (d-1 / d-7).

Data shown are the model's own forecasts, derived error statistics and realised auction prices
under their source licences (historical days: Ember European wholesale electricity price data,
CC BY 4.0; newest days: Nord Pool N2EX, rolling 60-day window).
Research project; no trading advice, no warranty.

Site: https://timlouiswilken.github.io/gb-dayahead-forecast/
Research repo (code, methodology, results): https://github.com/TimLouisWilken/gb-dayahead-research
