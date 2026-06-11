---
name: quant-real-factor-5d-volume-confirmed-drawdown-from-high
description: Use when computing the 5D Volume Confirmed Drawdown From High factor from user-supplied real OHLCV data or reviewing its bundled real-data validation metrics.
metadata:
  organization: QuantSkills
  organization_url: https://github.com/quantskills
  repository: skill-quant-factor-risk-pattern-alpha
  repository_url: https://github.com/quantskills/skill-quant-factor-risk-pattern-alpha
  collection: risk-pattern-alpha
  factor_id: R227
  category: Drawdown
---

# 5D Volume Confirmed Drawdown From High

Use this Skill to compute `5日量能确认距高点回撤` / `5D Volume Confirmed Drawdown From High` from caller-provided OHLCV data.

## Workflow

1. Load a `pandas.DataFrame` with `open`, `high`, `low`, `close`, `volume`; include `date` and `symbol` for cross-sectional research.
2. Call `scripts/factor.py::compute_factor(df)` to compute the factor column.
3. Call `generate_signals(df)` for a simple rank-based long/short signal.
4. Review `validation_real/report.md` before using the factor in a model.

## Runtime Contract

- Framework-neutral Python: `pandas` and `numpy`.
- The caller owns data vendor, universe, calendar, costs, slippage, and execution modeling.
