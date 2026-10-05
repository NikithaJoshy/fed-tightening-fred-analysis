# How Fed Rate Hikes Moved Through the Economy (FRED Data, 2018 to 2025)

A time-series and correlation analysis of how the Federal Reserve's 2021 to 2025 monetary tightening flowed through auto credit, consumer and business lending, and manufacturing, using Federal Reserve Economic Data (FRED).

*Texas A&M University, DAEN 400, Case Study 4, Fall 2025. Individual project.*

## Questions
How did rising policy rates show up in:
1. Auto credit and loan outcomes
2. Consumer credit and bank lending
3. Manufacturing and auto production

The analysis compares three periods: pre-trend, shock (COVID), and transmission.

## Data Engineering
- Pulled FRED series in four groups: general (Fed Funds, Treasury yields, unemployment, CPI, GDP), auto credit, consumer credit and bank lending (including Total Bank Credit and the share of banks tightening standards), and manufacturing and auto production indices.
- **Aligned mixed-frequency series** (daily, weekly, quarterly) to a monthly panel. Created average and end-of-quarter variants for Total Bank Credit.
- **Deflated nominal dollar series** to real December 2019 dollars using CPI, and **rebased indices** so that 2019-12 = 100.

## Key Results
| Variable | Correlation with Fed Funds Rate |
|---|---|
| 48-month auto loan rate | **+0.93** |
| Consumer Credit Index | **-0.64** |
| Business Loans Index | -0.46 |
| Banks tightening standards (%) | +0.33 |
| Auto loan/sales index | -0.27 |

| Period | Fed Funds (avg %) | Auto Loan Rate (avg %) | Manufacturing IP | Motor Vehicle IP |
|---|---|---|---|---|
| Pre-Trend | 1.91 | 5.20 | 101.1 | 102.4 |
| Shock | 0.05 | 5.29 | 72.5 | 20.4 |
| Transmission | 2.79 | 6.63 | 98.8 | 101.0 |

- Borrowing costs tracked policy rates almost one-for-one, while consumer and business credit contracted.
- Manufacturing recovered after COVID but stayed slightly below pre-pandemic levels as financing costs rose.
- Treasury yields rose above 5% while unemployment stayed relatively stable, a delayed labor-market response.

## Recommendations
Gradual rate adjustments, targeted credit programs for auto manufacturing and small businesses, adaptive lending standards, and clearer Fed communication. The report includes estimated dollar impacts.

## Tech Stack
Python, pandas, matplotlib, seaborn, Jupyter

## Repository Contents
- `notebooks/fred_monetary_tightening.ipynb`: data prep, deflation and rebasing, plots, correlations
- `reports/FRED_Monetary_Tightening_Report.pdf`: technical report
- `reports/FRED_Monetary_Tightening_Presentation.pdf`: slide deck

Data source: [FRED, Federal Reserve Bank of St. Louis](https://fred.stlouisfed.org/)
