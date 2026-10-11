# GB day-ahead power price forecast

Automatically published every morning (~08:50 UK time, before EPEX/N2EX gate closure) by an
online-learning research pipeline:

- **Point forecast**: Bernstein Online Aggregation over 6 selected members
  (LSTM+RF correction, gradient boosting, Transformer, LEAR, merit-order regression, Chronos-Bolt),
  each retrained/updated daily on a strict 07:30 UTC D-1 information set (no look-ahead).
- **Quantiles**: Quantile Regression Averaging over 13 members plus two dedicated
  GBM tail forecasts (QRA-15), calibrated with adaptive conformal inference.
- **Benchmark**: realised daily MAE is published against the standard naive (d-1 / d-7).

Data shown are the model's own forecasts and derived error statistics.
Raw exchange prices are not redistributed. Research project - no trading advice, no warranty.

Site: https://timlouiswilken.github.io/gb-dayahead-forecast/
