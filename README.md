# skill-quant-factor-risk-pattern-alpha

`skill-quant-factor-risk-pattern-alpha` 是 QuantSkills 组织的风险状态与形态类因子 Skill 仓库，收录用于刻画波动率、K 线形态、震荡状态和回撤压力的 OHLCV 因子。

QuantSkills GitHub 组织：https://github.com/quantskills

这个仓库适合用于研究：

- 波动率状态
- K 线实体、影线和缺口形态
- RSI 与随机指标等震荡状态
- 回撤和风险压力

## QuantSkills 因子库导航

QuantSkills 将这批 OHLCV 因子按研究用途拆分为三个公开 Skill 仓库：

- [`skill-quant-factor-directional-alpha`](https://github.com/quantskills/skill-quant-factor-directional-alpha)：方向类，包含趋势、动量、反转、突破和通道位置因子。
- [`skill-quant-factor-risk-pattern-alpha`](https://github.com/quantskills/skill-quant-factor-risk-pattern-alpha)：风险与形态类，包含波动率、K 线形态、震荡和回撤因子。
- [`skill-quant-factor-volume-stat-alpha`](https://github.com/quantskills/skill-quant-factor-volume-stat-alpha)：量能与统计类，包含成交量、量价关系、流动性、时序排名和收益分布因子。

本仓库是其中的风险与形态类因子库，不代表 QuantSkills 因子库的全部内容。

## 仓库内容

本仓库包含 `288` 个因子 Skill，保留原始因子编号。

| 类别 | 数量 | 说明 |
|---|---:|---|
| Volatility | 96 | ATR 占比、振幅占比、实现波动率、下行波动率 |
| Pattern | 96 | 缺口、日内收益、上影线压力、下影线支撑 |
| Oscillator | 72 | RSI 强度、RSI 反转、随机区间位置 |
| Drawdown | 24 | 距高点回撤等风险状态 |

## 单个因子结构

每个因子都是一个独立 Skill 文件夹，统一放在 `factors/` 目录下，文件夹命名格式为 `<factor_id>-<english_slug>`：

```text
factors/
  R014-5d-z-scored-atr-ratio/
    SKILL.md
    README.md
    scripts/
      factor.py
      validate.py
    validation_real/
      result.json
      report.md
    references/
      formula.md
    agents/
      openai.yaml
```

## 数据要求

因子代码只依赖标准 OHLCV 字段：

```text
date, symbol, open, high, low, close, volume
```

推荐额外保留：

```text
market
```

## 验证口径

本仓库因子已使用真实行情面板验证：

- A股：98 个标的
- 美股：50 个标的
- 样本区间：2021-01-04 到 2026-06-10
- 验证结果：288 / 288 pass

验证指标包括覆盖率、5 日 Rank IC、5 日 ICIR、五分组 Q5-Q1 收益差、Top 组换手率和无未来函数检查。

## 使用方式

进入任意因子目录后，可以直接运行自检：

```powershell
$env:PYTHONUTF8='1'
python .\scripts\validate.py
```

在代码中调用：

```python
from scripts.factor import compute_factor

result = compute_factor(df)
```

其中 `df` 是用户自己的 OHLCV 数据。

## 索引文件

- `factor_index.json`：本仓库全部因子的元数据索引
- `validation_summary_real.json`：本仓库全部因子的真实行情验证汇总
- `repo_summary.json`：仓库级别统计信息
