# CAPM on Russian Stock Market

Empirical test of the Capital Asset Pricing Model (CAPM) on the Moscow Exchange (MOEX) using monthly stock returns.

## Methods
- **Time-series OLS** with HAC standard errors (Newey-West, 3 lags)
- **Fama-MacBeth two-pass regression**
- **GRS Test** (Gibbons, Ross, Shanken 1989)
- **Rolling betas** (24-month window)

## Key Results
- Sample: 26 stocks, February 2018 – May 2022 (52 months)
- GRS test rejects CAPM: p = 0.023
- γ₁ (market risk premium) is insignificant in Fama-MacBeth
- 3 out of 26 stocks have significant alphas

## Data
- Source: Yahoo Finance (`.ME` tickers)
- Market index: IMOEX (^MOEX)
- Risk-free rate: CBR key rate (monthly)
- Note: Yahoo Finance `.ME` data ends ~2022-07 due to sanctions/delisting

## Structure
```
capm_russia.ipynb           # main notebook (source)
capm_russia_executed.ipynb  # executed notebook with outputs
*.png                       # charts
```

## Possible Extensions
- Fama-French 3-factor model (SMB, HML for Russian market)
- Momentum factor (WML)
- Conditional CAPM
- Robustness check excluding 2022 sanctions period
- MOEX API (`moexalgo`) for 2022–2024 data
