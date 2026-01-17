# Crypto Statistical Arbitrage

This project explores statistical arbitrage strategies in cryptocurrency markets, focusing on momentum and short-term mean-reversion signals.

## Motivation
Cryptocurrency markets are relatively young and fragmented, making them fertile ground for statistical arbitrage. This project investigates whether momentum and reversal effects can be exploited after accounting for realistic execution costs.

## Strategies Explored
- Momentum strategies across multiple time horizons
- Short-term mean reversion during low-information periods
- Regime filters based on volatility and trading activity

## Data
- Price and volume data from Binance
- Assets include BTC, ETH, and selected liquid altcoins
- Frequency: 4-hour bars (initial analysis)

## Execution Assumptions
- Market orders: 20 bps total cost
- Limit orders: 7 bps commission

## Project Structure
- Notebooks for research and analysis
- Modular Python code for signals, backtesting, and evaluation
- Interactive results published via Datapane

## Status
wip — research notebook and backtests under active development.

