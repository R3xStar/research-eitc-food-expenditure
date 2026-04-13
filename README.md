# State EITC and Household Food Expenditure

Replication code and analysis for:

> **"The Impact of State Earned Income Tax Credit on Household Spending: Evidence from Low-Income Families"**  
> Rex W. Sitti — Old Dominion University  
> *Submitted to the Journal of Behavioral and Experimental Economics*

## Overview

This project estimates the effect of **state-level Earned Income Tax Credit (EITC)** expansions on household food expenditure patterns — specifically the tradeoff between food consumed at home versus food away from home. Using Consumer Expenditure Survey (CE Survey) microdata from 2004–2019 across 44 states, the analysis applies modern difference-in-differences methods to identify how income transfers shape food demand among low-income families.

## Research Question

Do state EITC expansions shift household food spending from food-away-from-home toward food-at-home — or vice versa — and does this vary by household income, demographics, and labor market conditions?

## Data

| Source | Description | Years |
|---|---|---|
| Consumer Expenditure Survey (CE Survey) | Household-level food expenditure microdata | 2004–2019 |
| NCSL / Tax Policy Center | State EITC generosity (% of federal credit) | 2004–2019 |
| BLS / FRED | State-level labor market controls | 2004–2019 |

> **Note:** CE Survey microdata must be downloaded directly from the [BLS website](https://www.bls.gov/cex/pumd.htm). Raw data files are not included in this repository.

## Methods

- **Two-Way Fixed Effects (TWFE):** Baseline DiD estimator with state and year fixed effects
- **De Chaisemartin & D'Haultfœuille (2020):** Heterogeneity-robust DiD estimator (`did_multiplegt` in Stata) to account for staggered treatment timing
- **Parallel trends diagnostics:** Event study plots and pre-trend tests

## Repository Structure

```
research-eitc-food-expenditure/
├── EITC_Expense_Updated.do     # Main Stata do-file: cleaning, merging, estimation
├── EITC_Expense_Updated.html   # Stata output log (HTML format)
└── README.md
```

## Software & Dependencies

**Stata** (primary analysis)
- `did_multiplegt` — De Chaisemartin & D'Haultfœuille DiD estimator
- `reghdfe` — High-dimensional fixed effects regression
- `coefplot` — Coefficient/event study plots
- `estout` / `outreg2` — Table export

## Status

🟡 Under review — *Submitted to Journal of Behavioral and Experimental Economics*

## Author

**Rex W. Sitti**  
Assistant Professor of Economics  
Strome College of Business, Old Dominion University  
rsitti@odu.edu | [Google Sites](https://sites.google.com/view/rexwsitti/home)

## Related Work

- *The Effect of Homeless Shelters on Property Values: Evidence from Seattle, WA* — [R3xStar/research-homeless-shelters-seattle](https://github.com/R3xStar)
- *Coastal Flooding and Housing Market Liquidity* — [R3xStar](https://github.com/R3xStar)
