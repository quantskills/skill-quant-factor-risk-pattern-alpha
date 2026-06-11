---
name: quant-real-factor-10d-compressed-drawdown-from-high
description: Use when computing the 10D Compressed Drawdown From High factor from user-supplied OHLCV data or reviewing its bundled real-data validation metrics.
metadata:
  organization: QuantSkills
  organization_url: https://github.com/quantskills
  repository: skill-quant-factor-risk-pattern-alpha
  repository_url: https://github.com/quantskills/skill-quant-factor-risk-pattern-alpha
  collection: risk-pattern-alpha
  factor_id: R788
  category: Drawdown
---

# 10D Compressed Drawdown From High

Use this Skill to compute `10日压缩距高点回撤` / `10D Compressed Drawdown From High` from caller-provided OHLCV data.

## Workflow

1. Load a `pandas.DataFrame` with `open`, `high`, `low`, `close`, `volume`; include `date` and `symbol` for cross-sectional research.
2. Call `scripts/factor.py::compute_factor(df)` to compute the factor column.
3. Call `generate_signals(df)` for a simple rank-based long/short signal.
4. Review `validation_real/report.md` before using the factor in a model.

## Runtime Contract

- Framework-neutral Python: `pandas` and `numpy`.
- The caller owns data vendor, universe, calendar, costs, slippage, and execution modeling.
