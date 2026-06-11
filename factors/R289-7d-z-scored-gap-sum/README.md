# 7日标准化缺口累积

中文 | [English](#english)

## 中文

`7日标准化缺口累积` 是一个使用真实行情验证过的 OHLCV 因子 Skill，属于 `形态` 类。

### 因子逻辑

```text
z(gap_sum, window=7)
```

该因子将 `缺口累积` 与 `标准化` 处理结合，观察价格、量能或波动状态在真实市场横截面中的可排序性。

### 真实数据检验

- 样本行数: `196935`
- 可用行数: `195152`
- 覆盖率: `0.9909`
- 5日 Rank IC 均值: `0.008056`
- 5日 ICIR: `0.3500`
- 五分组 Q5-Q1 均值: `0.000910`
- Top 组换手: `0.3409`
- 无未来函数检查: `True`
- 状态: `pass`

详细结果见 `validation_real/report.md` 和 `validation_real/result.json`。

## QuantSkills Collection

This factor is part of the QuantSkills `skill-quant-factor-risk-pattern-alpha` factor library. QuantSkills publishes three related OHLCV factor libraries: `skill-quant-factor-directional-alpha`, `skill-quant-factor-risk-pattern-alpha`, and `skill-quant-factor-volume-stat-alpha`. Choose the library that matches the research objective.

## English

`7D Z-Scored Gap Sum` is a real-data-validated framework-neutral OHLCV factor Skill in the `Pattern` family.

### Factor Logic

```text
z(gap_sum, window=7)
```

This factor combines `Gap Sum` with a `Z-Scored` transform to test whether the resulting price, volume, or volatility state is cross-sectionally sortable in real market data.

### Real-Data Validation

- Sample rows: `196935`
- Usable rows: `195152`
- Coverage: `0.9909`
- 5-day Rank IC mean: `0.008056`
- 5-day ICIR: `0.3500`
- Quintile Q5-Q1 mean: `0.000910`
- Top-quintile turnover: `0.3409`
- No-lookahead check: `True`
- Status: `pass`
