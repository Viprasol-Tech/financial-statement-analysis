# Example — Retailer Distress Review (Liquidity Decay, Z in Distress, M Flag)

> **Illustrative example.** "Meridian Retail Group" and all figures below are
> fictional, used to demonstrate the skill's output format. Not a real company
> and not investment advice.

## Header

| | |
|---|---|
| **Company** | Meridian Retail Group (illustrative) |
| **Sector** | Brick-and-mortar specialty retail |
| **Periods** | FY2023 → FY2024 (audited 10-K) |
| **Currency / units** | USD, millions |
| **Statements provided** | Income statement, balance sheet, cash-flow statement |
| **Altman variant** | **Z″** (non-manufacturer / retail) |

### Extracted line items (illustrative, $M)

| Item | FY2023 | FY2024 |
|---|---|---|
| Revenue | 2,400 | 2,520 |
| COGS | 1,560 | 1,714 |
| Gross profit | 840 | 806 |
| Operating income (EBIT) | 120 | 58 |
| Interest expense | 70 | 84 |
| Net income | 36 | 8 |
| Cash | 90 | 42 |
| Accounts receivable | 70 | 110 |
| Inventory | 420 | 560 |
| Total current assets | 600 | 730 |
| Total assets | 1,800 | 1,880 |
| Accounts payable | 280 | 250 |
| Current liabilities | 560 | 690 |
| Total debt | 820 | 940 |
| Total liabilities | 1,420 | 1,560 |
| Shareholders' equity | 380 | 320 |
| Retained earnings | 120 | 110 |
| CFO | 150 | 40 |
| Capex | 90 | 95 |
| D&A | 110 | 115 |

EBITDA FY2024 = EBIT (58) + D&A (115) = **173**.

## Scorecard

| Metric | Value (FY2024) | vs Benchmark | Trend |
|---|---|---|---|
| Current ratio | 1.06 | Watch → Concern | ↓ |
| Quick ratio | 0.25 | Concern | ↓ |
| Cash ratio | 0.06 | Concern | ↓ |
| Debt-to-equity | 2.94 | Concern | ↑ |
| Net debt / EBITDA | (940−42)/173 = 5.2× | Concern | ↑ |
| Interest coverage | 58/84 = 0.69× | Concern | ↓ |
| Gross margin | 32.0% (33.2%→32.0%) | Watch | ↓ |
| Operating margin | 2.3% (5.0%→2.3%) | Concern | ↓ |
| Net margin | 0.3% | Concern | ↓ |
| ROA | 0.4% | Concern | ↓ |
| ROE | 2.3% | Concern | ↓ |
| Inventory days (DIO) | 119 days (98→119) | Watch | ↑ |
| DSO | 16 days (11→16) | Watch | ↑ |
| Cash conversion cycle | 119 + 16 − 53 = 82 days | Watch | ↑ |

## DuPont (FY2024)

ROE = Net margin (0.3%) × Asset turnover (1.37) × Equity multiplier (5.26)
= **2.3%**.

The thin 2.3% ROE is being **propped up by a 5.26× equity multiplier** (heavy
leverage). Strip out the leverage and the underlying profitability (0.3% net
margin, 0.4% ROA) is barely positive — returns are "borrowed", not earned, and
the leverage that flatters ROE is the same leverage threatening solvency.

## Distress & Manipulation Scores

**Altman Z″** (6.56·X1 + 3.26·X2 + 6.72·X3 + 1.05·X4):

- X1 = WC/TA = (730−690)/1,880 = 0.0213 → 0.140
- X2 = RE/TA = 110/1,880 = 0.0585 → 0.191
- X3 = EBIT/TA = 58/1,880 = 0.0309 → 0.207
- X4 = Equity/Liabilities = 320/1,560 = 0.2051 → 0.215
- **Z″ ≈ 0.75** → **< 1.10 = Distress zone.** Razor-thin working capital,
  weak EBIT/assets, and a small equity cushion all point to elevated
  bankruptcy risk over the next ~2 years.

**Beneish M** (FY2023 → FY2024):

- **DSRI** = (110/2,520)/(70/2,400) = 1.497 → receivables growing far faster
  than sales (flag).
- **GMI** = 0.350/0.320 = 1.094 → margins deteriorating (flag).
- **SGI** = 2,520/2,400 = 1.05 → growth pressure.
- **TATA** = (NI − CFO)/TA = (8 − 40)/1,880 = −0.017 → accruals slightly
  negative this year, but the **inventory build (+140) and AR build (+40)** are
  the real working-capital tell.
- Net **M ≈ −1.60 (> −1.78) → likely manipulator flag tripped**, driven mainly
  by **DSRI and GMI**. Combined with the inventory/AR build and collapsing CFO,
  earnings quality is a genuine concern — treat as "look much harder".

## Cash-Flow Quality

- **CFO vs Net income:** CFO collapsed 150 → 40; CFO/NI = 40/8 = 5.0× looks high
  only because NI is near zero — in absolute terms CFO fell 73% while revenue
  rose, a serious divergence.
- **Accruals ratio:** (NI − CFO)/Avg assets = (8 − 40)/1,840 = **−1.7%** — not
  the warning here; the warning is the *inventory-funded* cash drain.
- **Free cash flow:** CFO − Capex = 40 − 95 = **−55M.** Negative FCF while
  carrying $940M of debt and only $42M cash.

## Prioritized Red Flags

1. **Interest coverage 0.69× (< 1×)** — EBIT no longer covers interest; the
   single most serious signal.
2. **Liquidity collapse** — cash 90 → 42, cash ratio 0.06, quick ratio 0.25;
   $250M+ current liabilities and a refinancing wall against $940M total debt.
3. **Inventory days 98 → 119 with flat real growth** — $140M inventory build is
   consuming cash and signals demand/obsolescence risk (markdown pressure
   ahead, explaining the gross-margin slip).
4. **Negative FCF (−55M)** against high leverage — the cash engine is in
   reverse.
5. **Beneish M flag + rising DSO** — earnings quality and revenue-recognition
   warrant scrutiny.

## Health Verdict

**Distressed.** Meridian Retail Group exhibits a textbook deterioration:
interest coverage has fallen below 1×, liquidity has collapsed (cash ratio
0.06, quick ratio 0.25), leverage is high and rising (net debt/EBITDA 5.2×,
D/E 2.9×), and a $140M inventory build has turned operating cash flow and free
cash flow sharply negative. The Altman Z″ of ~0.75 sits squarely in the
distress zone, and the Beneish M-score trips its threshold on receivable and
margin indices — so the modest reported net income is low quality. DuPont
confirms the thin ROE is leverage-driven, not earned. Absent a refinancing,
asset sale, or rapid inventory clear-down, solvency risk is material over the
next 12–24 months. *Illustrative; not investment advice.*
