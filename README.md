# Crypto Statistical Arbitrage

This project studies **statistical arbitrage strategies in cryptocurrency markets**, focusing on **cross-sectional momentum**, **short-term mean reversion**, and **risk-aware portfolio construction**.  
The emphasis is on **clean research methodology**, **real world impactful results**, and **managing risk**.

---

## Motivation

Cryptocurrency markets are:
- relatively young,
- fragmented across venues,
- continuously traded (24/7),

making them a strong candidate for **statistical arbitrage**.  
This project evaluates whether **momentum and reversal effects** persist after accounting for **execution delay, volatility scaling, and daily rebalancing**.

---

## Strategies Implemented

| Component | Description |
|--------|-------------|
| Cross-sectional momentum | Rank assets by recent average returns and trade winners vs losers |
| Mean reversion diagnostics | Test short-horizon reversals via lag and horizon sensitivity |
| Daily rebalancing | Portfolio weights updated once per UTC day (4h data) |
| Execution lag | Explicit delay to avoid look-ahead bias |
| Portfolio construction | Market-neutral, long/short, fully invested |
| Weighting schemes | Equal-weight, volatility-adjusted, Sharpe-aware (diagnostic) |
| Evaluation | Equity curves, Sharpe ratios, volatility, drawdowns |
| Outputs | Tables, plots, and interactive Datapane report |

---
### Data

- **Source:** Binance  
- **Assets:** BTC, ETH, BNB, ADA, XRP, DOT, MATIC  
- **Frequency:** 4-hour bars  
- **Time span:** Multi-year history with focused 6–12 month backtests  

---

## Weighting Schemes Compared

- **Equal weighting**
  - Assigns the same absolute weight to each asset
  - Simple and highly interpretable
  - Tends to over-allocate risk to high-volatility assets

- **Volatility-adjusted weighting**
  - Scales weights by inverse realized volatility
  - Produces more balanced risk exposure across assets
  - Results in smoother equity curves and better drawdown control
  - Requires reasonably stable volatility estimates

- **Sharpe-weighted weighting (diagnostic only)**
  - Scales weights by historical Sharpe ratios
  - Intuitively balances risk and return
  - Highly unstable and sensitive to lookback choice
  - Prone to overfitting and not suitable for production use

---

## Why Volatility-Adjusted Weighting?

- Reduces risk concentration compared to equal weighting
- Improves drawdown behavior during high-volatility regimes
- Less sensitive to regime shifts than equal-weight portfolios
- Maintains strong interpretability while improving realism
- Better aligned with production-style portfolio construction

---

## Portfolio Construction

- Dollar-neutral (long exposure = short exposure)
- Absolute weights normalized to sum to 1
- Rebalanced daily, held constant intraday
- Explicit tracking of:
  - positions (units),
  - holdings value,
  - cash,
  - total equity

---

## Execution Assumptions

| Execution Type | Cost Assumption |
|--------------|----------------|
| Market orders | ~20 bps all-in |
| Limit orders | ~7 bps commission |
| Signal delay | 1–2 bars (configurable) |

---

## Results Summary

- **Initial capital:** $1,000  
- **Final value (Jan 2026):** $1,160.69  
- **Total profit:** $160.69  
- **Total return:** **+16.1%**

These results reflect the performance of the daily-rebalanced, volatility-adjusted, market-neutral strategy over the evaluation period, before any additional transaction-cost sensitivity analysis.
