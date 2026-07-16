---
name: quant-factor-risk-pattern-alpha
description: Use when an agent needs a verified library of OHLCV risk-state and chart-pattern
  alpha factor Skills for volatility, K-line shape, shock, drawdown, and pressure
  analysis.
license: GPL-3.0-only
metadata:
  organization: QuantSkills
  organization_url: https://github.com/quantskills
  repository: skill-quant-factor-risk-pattern-alpha
  repository_url: https://github.com/quantskills/skill-quant-factor-risk-pattern-alpha
  project_type: skill
  collection: quant-factor-risk-pattern-alpha
  creator: abgyjaguo
  maintainer: abgyjaguo
quantSkills:
  project_type: skill
  category: factor
  tags:
  - alpha-factor
  - risk-pattern
  - ohlcv
  - volatility
  - drawdown
  platforms:
  - claude-code
  - codex
  - hermes
  - openclaw
  - cursor
  status: stable
  validation_level: verified
  maintainer_type: official
  summary_zh: 风险状态与形态类因子库：288 个独立 OHLCV 因子 Skill，真实行情验证 288/288 全部通过。
  summary_en: Risk-state and chart-pattern OHLCV alpha factor library with 288 factor
    Skills for volatility, K-line shape, shock, drawdown, and pressure analysis.
  license: GPL-3.0
---

```json qsh-form
{
  "version": 1,
  "task": {
    "placeholder": "补充要选择、检查或应用的风险状态与图形形态因子需求"
  },
  "fields": [
    {
      "key": "factor",
      "label": "因子名/主题线索 (可选)",
      "type": "text",
      "placeholder": "例如：波动类、K线形态类、回撤类、压力类",
      "help": "运行时经本库 factor_index.json 定位具体因子"
    },
    {
      "key": "expr",
      "label": "自定义因子表达式",
      "type": "textarea",
      "placeholder": "可选；填写时以表达式为分析对象"
    },
    {
      "key": "universe",
      "label": "股票池",
      "type": "select",
      "default": "000300.SH",
      "options": [
        { "value": "000300.SH", "label": "沪深300" },
        { "value": "000905.SH", "label": "中证500" },
        { "value": "399006.SZ", "label": "创业板指" },
        { "value": "000852.SH", "label": "中证1000" }
      ]
    },
    {
      "key": "horizon",
      "label": "预测周期",
      "type": "select",
      "default": "5",
      "options": [
        { "value": "1", "label": "未来 1 日" },
        { "value": "5", "label": "未来 5 日" },
        { "value": "10", "label": "未来 10 日" },
        { "value": "20", "label": "未来 20 日" }
      ]
    }
  ],
  "prompt_template": "{{#task}}任务与材料：\n{{task}}\n\n{{/task}}{{#attachments}}用户上传的材料（已放入工作区）：\n{{attachments}}\n\n{{/attachments}}请从 OHLCV 风险状态与图形形态因子库中选择、检查或应用因子。{{#factor}}因子名/主题线索：{{factor}}。{{/factor}}{{#expr}}以自定义表达式 {{expr}} 为准。{{/expr}}股票池为 {{universe}}，预测周期为 {{horizon}} 日。先通过 factor_index.json 定位并读取具体因子目录说明，说明波动、K 线形态、冲击、回撤或压力逻辑，并提示更换样本、数据商或假设后需要重新验证，输出中文报告。"
}
```

# Quant Factor Risk Pattern Alpha

Use this skill when an agent needs to select, inspect, or apply OHLCV risk-state and chart-pattern alpha factor Skills from this repository.

## Workflow

1. Read [README.md](README.md) for the repository-level inventory, validation scope, and market sample.
2. Use `factor_index.json` to locate the relevant factor family or individual factor directory.
3. Open the selected factor folder under the factors directory and follow its local instructions before writing or running code.
4. Treat validation metrics as historical research evidence, not investment advice. Re-run validation when the universe, time range, data vendor, or execution assumptions change.

## Scope

This repository focuses on volatility state, K-line shape, shock patterns, drawdown pressure, and other risk or pattern signals built from OHLCV data.
## Agent Compatibility

- Claude Code, Codex, Hermes, and OpenClaw can load this root folder as a collection skill, then drill into actors/*/SKILL.md.
- Cursor should use gents/cursor-rule.mdc and keep the full repository under .cursor/skills/quant-factor-risk-pattern-alpha.
- Agents without native skill discovery can paste gents/portable-loader.md.
