# Example — SaaS Company Review (Strong Margins, Cash Burn, Grey-Zone Z)

> **Illustrative example.** "NimbusOps Inc." and all figures below are
> fictional, used to demonstrate the skill's output format. Not a real company
> and not investment advice.

## Header

| | |
|---|---|
| **Company** | NimbusOps Inc. (illustrative) |
| **Sector** | B2B SaaS / cloud software |
| **Periods** | FY2023 → FY2024 (audited 10-K) |
| **Currency / units** | USD, thousands |
| **Statements provided** | Income statement, balance sheet, cash-flow statement |
| **Altman variant** | **Z″** (non-manufacturer, recurring-revenue model) |

### Extracted line items (illustrative, $000s)

| Item | FY2023 | FY2024 |
|---|---|---|
| Revenue | 180,000 | 252,000 |
| COGS | 36,000 | 48,000 |
| Gross profit | 144,000 | 204,000 |
| Operating expenses (S&M, R&D, G&A) | 150,000 | 206,000 |
| Operating income (EBIT) | (6,000) | (2,000) |
| Interest expense | 1,200 | 1,500 |
| Net income | (8,400) | (4,200) |
| Cash & ST investments | 70,000 | 52,000 |
| Accounts receivable | 30,000 | 46,000 |
| Total current assets | 104,000 | 102,000 |
| Total assets | 150,000 | 165,000 |
| Current liabilities (incl. deferred rev.) | 58,000 | 74,000 |
| Total debt | 20,000 | 25,000 |
| Total liabilities | 95,000 | 118,000 |
| Shareholders' equity | 55,000 | 47,000 |
| Retained earnings (deficit) | (40,000) | (44,200) |
| CFO | (3,000) | (12,000) |
| Capex | 4,000 | 6,000 |
| D&A | 5,000 | 7,000 |

EBITDA FY2024 = EBIT (−2,000) + D&A (7,000) = **5,000**.

## Scorecard

| Metric | Value (FY2024) | vs Benchmark | Trend |
|---|---|---|---|
| Current ratio | 1.38 | Watch | ↓ |
| Quick ratio | 1.38 (no inventory) | Healthy | ↓ |
| Cash ratio | 0.70 | Healthy | ↓ |
| Debt-to-equity | 0.53 | Healthy | ↑ |
| Net debt / EBITDA | (52−25)/... → net cash | Healthy | → |
| Interest coverage | −1.3× (EBIT negative) | Concern | ↑ |
| Gross margin | 81.0% | Healthy (SaaS) | ↑ |
| Operating margin | −0.8% | Watch (improving) | ↑ |
| Net margin | −1.7% | Watch (improving) | ↑ |
| ROE | −8.2% | Concern | ↑ |
| DSO | 55 → 67 days | Watch | ↑ |
| Asset turnover | 1.60 | Healthy | ↑ |

Notes: net cash position (cash 52,000 > debt 25,000), so net debt/EBITDA is not
meaningful — leverage is not the issue here. Interest coverage is negative only
because EBIT is still slightly negative.

## DuPont (FY2024)

ROE = Net margin (−1.7%) × Asset turnover (1.60) × Equity multiplier (3.09)
= **−8.2%**.

Negative ROE is driven entirely by the **negative net margin** (still
unprofitable), not by leverage or poor asset utilization — asset turnover of
1.6 is strong and the equity multiplier is moderate. The path to positive ROE
is operating leverage on the existing revenue base, not balance-sheet
engineering.

## Distress & Manipulation Scores

**Altman Z″** (6.56·X1 + 3.26·X2 + 6.72·X3 + 1.05·X4):

- X1 = WC/TA = (102,000−74,000)/165,000 = 0.170 → 1.115
- X2 = RE/TA = −44,200/165,000 = −0.268 → −0.873
- X3 = EBIT/TA = −2,000/165,000 = −0.012 → −0.081
- X4 = Equity/Liabilities = 47,000/118,000 = 0.398 → 0.418
- **Z″ ≈ 0.58** → below 1.10... **but** the accumulated deficit (X2) dominates,
  which is typical and benign for a venture-funded growth SaaS. Adjusting for
  the strong net-cash balance sheet, the practical read is **grey zone**, not
  imminent distress. *This is a known Altman limitation for pre-profit growth
  firms — flag, don't condemn.*

**Beneish M:** receivables outpaced sales (DSRI > 1, DSO 55 → 67) and accruals
were negative (NI −4,200 < CFO −12,000... CFO is *worse* than NI, so accruals
are negative → TATA low). Net **M ≈ −2.6 (< −1.78) → unlikely manipulator.**
The widening NI-vs-CFO gap here reflects working-capital growth (deferred
revenue collected slower, AR up), not income inflation.

## Cash-Flow Quality

- **CFO vs Net income:** CFO (−12,000) is *below* net income (−4,200) → CFO/NI
  divergence is unfavorable, driven by AR growth (DSO up 12 days) and slower
  collections.
- **Accruals ratio:** (NI − CFO)/Avg assets = (−4,200 − (−12,000))/157,500 =
  **+5.0%** — modestly positive; earnings quality is acceptable but worth
  watching as DSO rises.
- **Free cash flow:** CFO − Capex = −12,000 − 6,000 = **−18,000**. FCF margin
  −7.1%. Burn widened year over year.

## Prioritized Red Flags

1. **FCF burn widened** (−18,000 vs prior year) while revenue grew 40% — runway
   matters: at this burn, ~$52,000 cash ≈ < 3 years; financing/path-to-breakeven
   is the key risk.
2. **DSO rose 55 → 67 days** with revenue growth — monitor collections and
   billing terms; partly explains the CFO shortfall.
3. **Accumulated deficit** keeps Altman Z″ optically in the grey zone — normal
   for the model, but means no equity cushion from retained earnings.

## Health Verdict

**Adequate (improving).** NimbusOps shows excellent SaaS unit economics — 81%
gross margin, 1.6× asset turnover, a net-cash balance sheet, and a clearly
narrowing operating loss — but it is still pre-profit and free-cash-flow
negative, with widening burn and rising DSO. The grey-zone Altman Z″ is an
artifact of the accumulated deficit rather than genuine distress, and the
Beneish M-score is clean. The investment question is execution and runway —
whether operating leverage closes the loss before cash gets tight — not
solvency or earnings quality. *Illustrative; not investment advice.*
