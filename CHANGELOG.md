# Changelog

All notable changes to this project are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-06-12

### Added
- Initial release of the **financial-statement-analysis** Agent Skill.
- `skill.md` methodology with a 6-step workflow: scope & context, data
  extraction, ratio analysis, DuPont + distress/manipulation scores, red-flag
  scan, and a structured output format with a health verdict.
- **30+ ratios** across liquidity, solvency/leverage, profitability, and
  efficiency, each with formula, meaning, and sector-aware benchmark bands.
- **DuPont** 3-step and 5-step ROE decomposition.
- **Altman Z-score** (original manufacturing + Z″ non-manufacturer variant)
  with distress zones.
- **Beneish M-score** with all 8 components and the −1.78 threshold.
- Cash-flow quality checks (CFO vs net income, accruals ratio, free cash flow).
- Two worked example reports: a SaaS company (grey-zone Z) and a distressed
  retailer (Altman distress + Beneish flag).
- "Not investment advice" disclaimer in both `skill.md` and `README.md`.
- CI validator (`scripts/validate_skill.py`) and GitHub Actions workflow
  (`.github/workflows/validate.yml`).

[1.0.0]: https://github.com/Viprasol-Tech/financial-statement-analysis/releases/tag/v1.0.0
