# Beer Taxes and Traffic Deaths: A Panel Analysis of U.S. States (1982–1988)

Panel regression project for DIDA 383B at Binghamton University.

Question: Holding constant fixed state characteristics and nationwide yearly shocks, is a higher beer tax associated with fewer traffic deaths?

## Data
`Fatalities` dataset from the AER R package (Kleiber & Zeileis, 2008), originally
compiled by Ruhm (1996): 48 U.S. states, 1982–1988, 335 state-years after cleaning.

## Methods
- Pooled OLS, state fixed effects, random effects, and two-way (state + year) fixed effects using `plm`
- Model selection: F test, Breusch-Pagan LM, Hausman (standard and robust)
- Diagnostics: VIF, Breusch-Pagan, Wooldridge serial correlation, Pesaran CD, Shapiro-Wilk
- Correction: state-clustered (Arellano) standard errors

## Key findings
- The pooled model shows a misleading *positive* beer tax effect; within states the relationship is negative.
- Two-way FE: a $1 increase in the real beer tax per case is associated with 0.46 fewer deaths per
  10,000 residents (~22% of the mean), but the estimate is not significant with clustered SEs (p = 0.13).
- Traffic deaths are procyclical: they rise with income and fall with unemployment.

## Tools
R 4.3 · plm · AER · lmtest · sandwich · car · ggplot2
