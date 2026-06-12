# Financial Statement Analysis — Agent Skill

> Turn raw financials into a disciplined fundamental analysis: ratios, DuPont,
> Altman Z-score, Beneish M-score, red flags, and a clear health verdict.

[![GitHub stars](https://img.shields.io/github/stars/Viprasol-Tech/financial-statement-analysis?style=social)](https://github.com/Viprasol-Tech/financial-statement-analysis)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-Compatible-blueviolet)](https://github.com/Viprasol-Tech/financial-statement-analysis)
[![Metrics](https://img.shields.io/badge/Metrics-30%2B-green)](skill.md)
[![Models](https://img.shields.io/badge/Altman%20Z%20%2B%20Beneish%20M-blue)](skill.md)
[![Version](https://img.shields.io/badge/version-1.0.0-informational)](CHANGELOG.md)

**Works with:** Claude Code · Codex · Cursor · Copilot · Gemini CLI · 26+ tools
that support portable agent skills.

---

## Quick Install

Clone the skill into your agent's skills directory:

```bash
# Claude Code
git clone https://github.com/Viprasol-Tech/financial-statement-analysis \
  ~/.claude/skills/financial-statement-analysis

# Cursor / Codex / other tools — clone anywhere your tool loads skills from, e.g.
git clone https://github.com/Viprasol-Tech/financial-statement-analysis \
  ~/.config/skills/financial-statement-analysis
```

The skill is a single self-contained `skill.md` (plus examples) — no
dependencies, no install step, nothing to build.

## Try It

Paste a company's numbers (or a 10-K excerpt) and ask:

```
Analyze these financials — is this company financially healthy?
```

The skill will scope the company and sector, extract the line items, compute
the full ratio suite, run DuPont + Altman Z + Beneish M, scan for red flags,
and return a scorecard with a one-paragraph health verdict.

---

## Why This Exists

Reading a 10-K well is a repeatable, methodical process — but it's easy to
eyeball a single ratio, miss the trend, or trust a headline EPS that operating
cash flow doesn't support. Analysts and credit teams apply the *same* checklist
every time: liquidity, solvency, profitability, efficiency, an ROE
decomposition, a distress screen, an earnings-quality screen, and a red-flag
pass. This skill encodes that checklist so your agent runs it consistently,
shows the formulas, respects sector context, and never skips the cash-flow
quality check.

## What It Does

1. **Scopes** the company, sector, period(s), currency, and which statements
   you provided.
2. **Extracts** the exact line items the ratios need and flags anything missing
   or estimated.
3. **Computes 30+ ratios** across liquidity, solvency, profitability, and
   efficiency — each with its formula and a sector-aware benchmark band.
4. **Decomposes ROE** with 3- and 5-step DuPont to show whether returns are
   earned or borrowed.
5. **Screens for distress** (Altman Z / Z″) and **earnings manipulation**
   (Beneish M), with the right variant for the sector.
6. **Scans for red flags** and grades **cash-flow quality** (CFO vs net income,
   accruals ratio, free cash flow).
7. **Outputs a scorecard** and a single **Strong / Adequate / Weak /
   Distressed** verdict.

## Features

- **Full ratio suite** — current, quick, cash, working capital; debt/equity,
  debt/assets, interest coverage, net debt/EBITDA; gross/operating/net margin,
  ROA, ROE, ROIC; asset turnover, DIO/DSO/DPO, cash conversion cycle.
- **DuPont decomposition** — 3-step and 5-step ROE breakdown.
- **Altman Z-score** — original (manufacturing) and Z″ (non-manufacturing /
  private / emerging-market) variants with distress zones.
- **Beneish M-score** — all 8 components and the −1.78 manipulation threshold.
- **Red-flag scan** — revenue/CFO divergence, rising DSO & inventory, goodwill
  bloat, debt walls, recurring "one-time" charges, and more.
- **Sector-aware benchmarks** — thresholds note where the default shifts by
  industry (a 0.8 current ratio is fine for a utility, not a retailer).

### Example benchmark table

| Ratio | Formula | Healthy | Watch | Concern |
|---|---|---|---|---|
| Current ratio | Current assets ÷ Current liabilities | ≥ 1.5 | 1.0–1.5 | < 1.0 |
| Interest coverage | EBIT ÷ Interest expense | > 4× | 2–4× | < 2× |
| Net debt / EBITDA | (Debt − Cash) ÷ EBITDA | < 2× | 2–4× | > 4× |
| Operating margin | Operating income ÷ Revenue | > 15% | 5–15% | < 5% |
| ROE | Net income ÷ Avg equity | > 15% | 8–15% | < 8% |

*Bands are general heuristics; the skill adjusts for sector context.*

See full worked reports in **[examples/](examples/)**:
- [SaaS company review](examples/saas-company-review.md) — strong margins,
  cash burn, Altman Z in the grey zone.
- [Retailer distress review](examples/retailer-distress-review.md) —
  deteriorating liquidity, Altman Z in distress, Beneish M flag.

---

## Not Investment Advice

This skill provides **educational financial analysis only** — not investment,
legal, or accounting advice. Ratios and scores are heuristics that need sector
and qualitative context; the Altman Z and Beneish M models are screens with
known false positives. Always verify figures against the **audited source**
(the filed 10-K/10-Q) and consult a licensed professional before making any
investment or credit decision. **Not affiliated with or endorsed by Anthropic.**

---

## Contact — Viprasol Tech Private Limited
- 🌐 Website: [viprasol.com](https://viprasol.com)
- ✉️ Email: [support@viprasol.com](mailto:support@viprasol.com)
- 💬 Telegram: [t.me/viprasol_help](https://t.me/viprasol_help) · 📱 WhatsApp: +91 96336 52112
- 🐙 GitHub: [@Viprasol-Tech](https://github.com/Viprasol-Tech) · 💼 [LinkedIn](https://www.linkedin.com/in/viprasol/) · 𝕏 [@viprasol](https://twitter.com/viprasol)

> *Viprasol Tech — fintech software, AI agents, algorithmic trading systems, and B2B SaaS.*

## License
[MIT](LICENSE) © 2025 Viprasol Tech Private Limited
