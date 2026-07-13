# TCS — 3-Statement DCF Model

A fully linked 3-statement financial model (Income Statement, Balance Sheet, Cash Flow) and DCF valuation for Tata Consultancy Services, built from scratch in Excel using public filings.

## What's in this model

- **Historical financials (FY22–FY26):** actual consolidated results, sourced from screener.in and cross-checked against TCS's quarterly results releases
- **5-year forecast (FY27E–FY31E):** driven entirely by an Assumptions tab - revenue growth, margins, tax rate, capex, and working capital ratios
- **WACC build:** CAPM-based cost of equity, post-tax cost of debt, weighted by market value of equity and debt
- **DCF valuation:** Free Cash Flow to Firm, discounted at WACC, terminal value via Gordon Growth, bridged to an implied share price
- **Sensitivity grid:** implied share price across a range of WACC and terminal growth combinations
- **Revolver / cash-sweep mechanism:** the balance sheet resolves its own funding gap through a plug that draws on a revolver when cash is short and builds cash when there's a surplus - including the circular reference this creates between interest expense and the revolver balance, solved via iterative calculation

## Structure

| Tab | Purpose |
|---|---|
| `ReadMe` | Color legend, sources, and a guide to using the model |
| `Assumptions` | Every forecast driver and WACC input in one place |
| `Income Statement` | Historical + forecast P&L |
| `Balance Sheet` | Historical + forecast balance sheet, including the revolver/cash plug |
| `Cash Flow` | Historical + forecast cash flow, indirect method |
| `DCF Valuation` | FCFF build, discounting, terminal value, implied share price |
| `Sensitivity` | WACC × terminal growth grid |

## Color convention

- **Blue text** — hardcoded input (historical actual or typed assumption)
- **Black text** — formula referencing the same sheet
- **Green text** — formula linking to another sheet
- **Yellow fill** — key assumption, meant to be edited
- **Light blue fill** — subtotal/total row
- **Light red fill** — balance or sanity check

## Key output (base case)

- WACC: ~11.2%
- Implied share price: ~₹2,220
- vs. market price of ₹1,983 (as of Jul 2026): ~12% upside
- Terminal value as % of enterprise value: ~76% (within the typical 65–85% range for a 5-year DCF)

## Known limitations

- Beta (0.65) and India equity risk premium (7.0%) are reasonable placeholders, not pulled from a terminal - worth refining with a current source
- Revenue growth tapering from 8% to 6% is a judgment call based on recent trends, not a formula
- This is a single-scenario base case; no explicit bull/bear case is built in (the Sensitivity tab partially substitutes for this)

## Data sources

- Historical financials: [screener.in/company/TCS/consolidated](https://www.screener.in/company/TCS/consolidated/)
- Share price & market cap: [screener.in](https://www.screener.in/company/TCS/consolidated/) , close of 1 Jul 2026
- India 10-year G-Sec yield: [tradingeconomics.com](https://www.tradingeconomics.com) , early Jul 2026

---

Built as a self-directed learning project to understand 3-statement modeling and DCF mechanics end-to-end - not copied from a template.
