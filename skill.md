---
name: financial-statement-analysis
description: Analyze company financial statements — liquidity, solvency, profitability, and efficiency ratios, DuPont, Altman Z-score, and Beneish M-score. Surfaces red flags and an earnings-quality check with sector benchmarks. Use for fundamental analysis, due diligence, credit review, or investment screening.
version: 1.0.0
---

# Financial Statement Analysis

A structured methodology for fundamental analysis of a company's financial
statements. Given a 10-K/10-Q, an income statement, a balance sheet, a
cash-flow statement, or a handful of key numbers, this skill produces a
disciplined read of **liquidity, solvency, profitability, efficiency**, an
ROE decomposition (**DuPont**), distress and earnings-manipulation scores
(**Altman Z**, **Beneish M**), a **red-flag scan**, and a one-paragraph
**health verdict** — all grounded in standard, real methodology with
sector-aware benchmarks.

> **Not investment advice.** This is an educational analytical framework. It
> does not account for forward guidance, qualitative moats, management quality,
> macro conditions, or your risk tolerance. Always verify numbers against the
> audited source and consult a licensed professional before acting.

---

## When to Activate

Activate this skill when the user:

- Shares a company's financials (10-K, 10-Q, annual report, income statement,
  balance sheet, cash-flow statement) and asks whether the company is healthy,
  improving, risky, or worth investing in.
- Asks for ratio analysis, fundamental analysis, due diligence, credit review,
  or investment screening on a named company or pasted figures.
- Wants to compare a company against peers or sector norms.
- Asks "are these numbers a red flag?", "is the earnings quality good?",
  "what is the Altman Z-score / Beneish M-score?", or "is this company likely
  to go bankrupt / manipulating earnings?".

If only a single number is given (e.g. just revenue), ask for the minimum line
items needed (see Step 2) before computing ratios. Do not fabricate inputs.

---

## Step 1: Scope & Context

Before any math, establish and restate the context so the analysis is anchored:

| Field | Why it matters |
|---|---|
| **Company / ticker** | Identifies the entity; enables peer lookup. |
| **Sector / industry** | Benchmarks are sector-specific (a 0.5 current ratio is fine for a utility, alarming for a retailer). |
| **Period(s)** | One period gives a snapshot; 3–5 years/quarters reveal **trend**, which matters more than any single ratio. |
| **Currency & units** | USD thousands vs millions vs reported FX changes every number. State it explicitly. |
| **Audited / unaudited** | Audited annual (10-K) is the most reliable; interim/management figures carry more uncertainty. |
| **Statements provided** | Some ratios need all three statements (e.g. accruals needs income + cash flow). Note what's missing. |
| **Fiscal-year quirks** | Non-calendar fiscal years, 52/53-week retailers, recent IPO/SPAC, M&A in the period. |

State each explicitly in the output header. If the sector is unknown, ask —
benchmarks are meaningless without it.

---

## Step 2: Data Extraction

Pull the specific line items the ratios need. Flag anything missing or
estimated, and note any restatements.

**Income statement:** Revenue (net sales), COGS, Gross profit, Operating
expenses (SG&A, R&D), Operating income (EBIT), Interest expense, Pre-tax
income, Income tax, **Net income**; plus **Depreciation & amortization** (for
EBITDA — often only on the cash-flow statement).

**Balance sheet:** Cash & equivalents, Short-term investments, Accounts
receivable, Inventory, Total current assets; Total assets; PP&E (net),
Goodwill & intangibles; Accounts payable, Short-term debt / current portion of
long-term debt, Total current liabilities; Long-term debt, Total liabilities;
**Total shareholders' equity**; retained earnings; shares outstanding.

**Cash-flow statement:** **Cash flow from operations (CFO)**, Capital
expenditures (capex), Cash flow from investing, Cash flow from financing,
dividends paid.

Rules:
- **Use averages for balance-sheet items in ratios that mix flow and stock.**
  ROA, ROE, asset turnover, inventory days, DSO, DPO all divide a flow (a full
  period of income/sales/COGS) by a balance — use the **average of beginning
  and ending** balance, e.g. `(opening + closing) / 2`, when both are
  available. Note when you only had a closing balance.
- **EBITDA = EBIT + D&A.** EBIT = Operating income. If "operating income"
  bundles unusual items, normalize and say so.
- **Flag estimates.** If a number is derived or assumed, mark it `(est.)`.
- **Note restatements / one-offs.** Prior-period restatements, impairments,
  litigation charges, and discontinued operations distort trend; call them out.
- **Watch sign conventions.** Capex and dividends are usually shown negative on
  the cash-flow statement; FCF = CFO − capex (capex as a positive magnitude).

---

## Step 3: Ratio Analysis

Compute the four groups below. For each ratio: the **formula**, **what it
means**, and a **benchmark band**. Benchmark bands are *general* — they shift
by sector, so the "sector note" column flags where the default lies.

> Convention: **Healthy** = typically comfortable; **Watch** = monitor / trend
> matters; **Concern** = often a problem absent a sector-specific reason.
> These are heuristics, not hard rules — context overrides the table.

### 3a. Liquidity — can it pay near-term bills?

| Ratio | Formula | What it means | Healthy | Watch | Concern | Sector note |
|---|---|---|---|---|---|---|
| **Current ratio** | Current assets ÷ Current liabilities | Short-term coverage | ≥ 1.5 | 1.0–1.5 | < 1.0 | Retail/utilities run lean (<1.0 normal); software runs high |
| **Quick ratio** (acid test) | (Current assets − Inventory) ÷ Current liabilities | Coverage excluding hard-to-sell inventory | ≥ 1.0 | 0.7–1.0 | < 0.7 | Inventory-heavy firms (retail, industrials) sit lower |
| **Cash ratio** | (Cash + Short-term investments) ÷ Current liabilities | Coverage from cash alone | ≥ 0.5 | 0.2–0.5 | < 0.2 | Very conservative measure; most healthy firms are < 1.0 |
| **Working capital** | Current assets − Current liabilities | Absolute cushion ($) | > 0 & growing with sales | flat | negative & worsening | Negative can be *strong* for cash-upfront models (e.g. Amazon, SaaS) |

### 3b. Solvency / Leverage — can it survive its debt?

| Ratio | Formula | What it means | Healthy | Watch | Concern | Sector note |
|---|---|---|---|---|---|---|
| **Debt-to-equity** | Total debt ÷ Total equity | Leverage vs owners' capital | < 1.0 | 1.0–2.0 | > 2.0 | Banks/utilities/REITs normally run far higher |
| **Debt-to-assets** | Total debt ÷ Total assets | Share of assets financed by debt | < 0.4 | 0.4–0.6 | > 0.6 | — |
| **Interest coverage** (TIE) | EBIT ÷ Interest expense | How many times earnings cover interest | > 4× | 2–4× | < 2× | < 1.5× is a serious distress signal |
| **Net debt / EBITDA** | (Total debt − Cash) ÷ EBITDA | Years of EBITDA to repay net debt | < 2× | 2–4× | > 4× | LBOs/telecom tolerate 4–6×; > 6× is stretched |
| **Equity ratio** | Equity ÷ Total assets | Solvency cushion | > 0.5 | 0.3–0.5 | < 0.3 | — |

### 3c. Profitability — does it make money, and how well?

| Ratio | Formula | What it means | Healthy | Watch | Concern | Sector note |
|---|---|---|---|---|---|---|
| **Gross margin** | Gross profit ÷ Revenue | Pricing power / unit economics | sector-relative | declining | thin & falling | Software 70–90%; grocery/retail 20–30%; the *trend* matters most |
| **Operating margin** | Operating income ÷ Revenue | Core operating efficiency | > 15% | 5–15% | < 5% | Highly sector-dependent |
| **Net margin** | Net income ÷ Revenue | Bottom-line profitability | > 10% | 3–10% | < 0% | — |
| **ROA** | Net income ÷ Avg total assets | Profit per $ of assets | > 5% | 2–5% | < 2% | Asset-light (software) high; asset-heavy (utilities) low |
| **ROE** | Net income ÷ Avg equity | Profit per $ of equity | > 15% | 8–15% | < 8% | Beware ROE inflated by heavy leverage — check DuPont |
| **ROIC** | NOPAT ÷ Invested capital | Return vs cost of capital | > WACC (≈ >10%) | ≈ WACC | < WACC | NOPAT = EBIT × (1 − tax rate); Invested capital = Debt + Equity − Cash |

### 3d. Efficiency — how hard do assets and working capital work?

| Ratio | Formula | What it means | Healthy | Watch | Concern | Sector note |
|---|---|---|---|---|---|---|
| **Asset turnover** | Revenue ÷ Avg total assets | Sales generated per $ of assets | > 1.0 | 0.5–1.0 | < 0.5 | Retail high (>2); capital-intensive low (<0.5) |
| **Inventory days (DIO)** | Avg inventory ÷ COGS × 365 | Days to sell inventory | sector-relative | rising vs sales | rising sharply | Lower = leaner; spikes signal demand/obsolescence problems |
| **DSO** (receivable days) | Avg AR ÷ Revenue × 365 | Days to collect cash | sector-relative | rising | rising sharply | Rising DSO with flat sales = collection/channel-stuffing risk |
| **DPO** (payable days) | Avg AP ÷ COGS × 365 | Days taken to pay suppliers | moderate | very high | stretching abnormally | Very high DPO can mask liquidity stress |
| **Cash conversion cycle** | DIO + DSO − DPO | Days cash is tied up in operations | low / negative | rising | rising sharply | Negative CCC (collect before you pay) is a strength |

> When a ratio mixes an income-statement flow with a balance-sheet stock, use
> the **average** balance over the period (Step 2).

---

## Step 4: DuPont + Distress / Manipulation Scores

### 4a. DuPont decomposition of ROE

**3-step:** ROE = **Net margin × Asset turnover × Equity multiplier**

```
ROE = (Net income / Revenue) × (Revenue / Avg assets) × (Avg assets / Avg equity)
        └ profitability ┘      └ efficiency ┘            └ leverage ┘
```

**5-step (separates tax and interest drag):**

```
ROE = Tax burden × Interest burden × Operating margin × Asset turnover × Equity multiplier
    = (NI/EBT)  × (EBT/EBIT)      × (EBIT/Revenue)    × (Revenue/Avg assets) × (Avg assets/Avg equity)
```

**Why:** DuPont shows *where* ROE comes from. A 20% ROE built on a 5×
equity multiplier (heavy leverage) is far riskier than the same 20% built on
strong margins. Always check whether ROE is "earned" (margins/efficiency) or
"borrowed" (leverage).

### 4b. Altman Z-score — distress / bankruptcy risk

**Original (manufacturing / public):**

```
Z = 1.2·X1 + 1.4·X2 + 3.3·X3 + 0.6·X4 + 1.0·X5

X1 = Working capital / Total assets
X2 = Retained earnings / Total assets
X3 = EBIT / Total assets
X4 = Market value of equity / Total liabilities
X5 = Revenue / Total assets
```

**Zones:** **Safe > 2.99** · **Grey 1.81 – 2.99** · **Distress < 1.81**

**Z″ variant — non-manufacturers, service firms, private, and emerging
markets** (drops X5 sales-turnover term; uses book equity in X4):

```
Z'' = 6.56·X1 + 3.26·X2 + 6.72·X3 + 1.05·X4

X4 = Book value of equity / Total liabilities
```

**Z″ zones:** **Safe > 2.60** · **Grey 1.10 – 2.60** · **Distress < 1.10**

Use **Z″** for SaaS, retail, services, banks-adjacent, private companies, or
anywhere a market cap isn't available. State which variant you used and why.

### 4c. Beneish M-score — earnings-manipulation likelihood

Probabilistic model flagging the likelihood that earnings have been
manipulated. Needs two consecutive years (t and t−1).

```
M = -4.84 + 0.920·DSRI + 0.528·GMI + 0.404·AQI + 0.892·SGI
        + 0.115·DEPI − 0.172·SGAI + 4.679·TATA − 0.327·LVGI
```

**8 components:**

| Var | Name | Formula (year t vs t−1) | Flag when |
|---|---|---|---|
| **DSRI** | Days Sales in Receivables Index | (AR_t/Rev_t) ÷ (AR_{t-1}/Rev_{t-1}) | > 1 (receivables outpacing sales) |
| **GMI** | Gross Margin Index | GM_{t-1} ÷ GM_t | > 1 (margins deteriorating) |
| **AQI** | Asset Quality Index | (1 − (CA+PPE)/TA)_t ÷ same_{t-1} | > 1 (more soft/intangible assets) |
| **SGI** | Sales Growth Index | Rev_t ÷ Rev_{t-1} | > 1 (growth pressure to manage) |
| **DEPI** | Depreciation Index | DepRate_{t-1} ÷ DepRate_t | > 1 (slowing depreciation) |
| **SGAI** | SG&A Index | (SGA/Rev)_t ÷ same_{t-1} | > 1 |
| **TATA** | Total Accruals to Total Assets | (ΔWorking capital − ΔCash − Dep) / TA, or (NI − CFO)/TA | high positive (accruals-driven income) |
| **LVGI** | Leverage Index | Leverage_t ÷ Leverage_{t-1} | > 1 |

**Threshold:** **M > −1.78 ⇒ likely manipulator** (more negative = cleaner).
TATA (accruals) and DSRI usually drive the score; a high M almost always
coincides with net income running well ahead of operating cash flow.

> The M-score is a *screen*, not a verdict — it flags statistical similarity to
> known manipulators and produces false positives (especially for fast-growing
> firms). Treat a trip as "look harder", not "fraud".

---

## Step 5: Red-Flags Quick Scan

Scan for these classic deterioration / quality signals. Each is a prompt to
investigate, not an automatic condemnation:

- **Revenue up but CFO down / flat** — earnings not converting to cash.
- **Rising DSO or inventory days vs sales** — channel stuffing, demand
  softening, collection problems, or obsolescence.
- **Widening gap between net income and operating cash flow** — accruals-heavy
  earnings; low earnings quality (see accruals ratio in Step 6).
- **Ballooning goodwill / intangibles** — acquisition-driven growth; impairment
  risk if acquired businesses underperform.
- **Debt maturities > cash + expected CFO** — refinancing/liquidity wall;
  check the maturity schedule.
- **Frequent "one-time" / restructuring charges** — recurring "non-recurring"
  items inflate adjusted earnings vs GAAP.
- **Negative & worsening working-capital trend** — unless the business model is
  structurally cash-upfront (verify).
- **Aggressive revenue recognition** — bill-and-hold, long-dated contracts
  pulled forward, bundled deals, rising "unbilled receivables".
- **Margin expansion with no operational explanation**, gross margin diverging
  from peers, or capitalizing costs that peers expense.
- **Rising leverage while profitability falls**, interest coverage trending
  toward < 2×, or dividends/buybacks funded by debt.

---

## Step 6: Output Format

Produce the report in this order:

### 1. Header
Company · sector · period(s) · currency/units · audited? · statements
provided · variant choices (which Altman Z used and why).

### 2. Scorecard table
One row per key metric; columns: **Metric · Value · vs Benchmark
(Healthy/Watch/Concern) · Trend** (use ↑ ↓ → arrows across periods).

| Metric | Value | vs Benchmark | Trend |
|---|---|---|---|
| Current ratio | 1.8 | Healthy | ↑ |
| Net debt/EBITDA | 3.4× | Watch | ↑ |
| Operating margin | 18% | Healthy | → |
| ROE | 22% | Healthy | ↑ |
| DSO | 64 days | Watch | ↑ |

### 3. DuPont readout
3-step (and 5-step if data allows). State whether ROE is margin-driven,
efficiency-driven, or leverage-driven.

### 4. Distress & manipulation scores
- **Altman Z (variant) = value → zone** with a plain-English read.
- **Beneish M = value → likely / unlikely manipulator**, naming the top 1–2
  components driving it.

### 5. Cash-flow quality
- **CFO vs Net income** (CFO/NI ratio; healthy ≈ ≥ 1.0).
- **Accruals ratio** = (Net income − CFO) ÷ Avg total assets. High positive =
  lower earnings quality.
- **Free cash flow** = CFO − Capex; note FCF margin and whether it's positive
  and growing.

### 6. Prioritized red-flags list
Most material first, each with the evidence (the numbers) behind it.

### 7. Health verdict (one paragraph)
Conclude with exactly one rating and a one-paragraph justification:

- **Strong** — healthy across liquidity, solvency, profitability; Z in Safe
  zone; clean M; CFO ≥ NI; no material red flags.
- **Adequate** — generally sound with one or two watch items; Z in Safe/upper
  Grey; manageable leverage.
- **Weak** — multiple watch/concern ratios, Z in Grey, thinning margins or
  rising leverage, or earnings-quality concerns.
- **Distressed** — Z in Distress zone, interest coverage < 1.5×, liquidity
  crunch, and/or M-score flag with corroborating red flags.

---

## Disclaimer

This skill provides **educational financial analysis, not investment, legal, or
accounting advice.** Ratios and scores are heuristics that require sector and
qualitative context; the Altman Z and Beneish M models are screens with known
false positives and were calibrated on historical datasets that may not fit a
given firm. Always verify every figure against the **audited primary source**
(the filed 10-K/10-Q), consider forward-looking and qualitative factors the
statements don't capture, and consult a licensed financial professional before
making any investment or credit decision. This skill is **not affiliated with or
endorsed by Anthropic** or any data provider.
