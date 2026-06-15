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
