---

# Variance Swap Hedging Analysis

## Overview

This repository contains an analysis of a potential trade aimed to hedge the risk from a $1M Vega notional in a 3-month $SPX Variance swap with a vol strike of 20%. Utilizing historical SPY prices and SPY options data, the project evaluates the realized volatility, computes the variance swap payout, calculates implied volatility, and analyzes the Vega exposure before and after considering a broker's trade offer.

## Data

- **SPY Prices:** Historical daily SPY prices for the period from September to December 2022.
- **SPY Options Data:** Used to compute the implied volatility which informs the Vega exposure from the broker's trade offer.
- **Duration:** 3 months (September to December 2022).

## Key Computations

1. **Realized Volatility:**
   - Daily log returns of the SPY prices are calculated.
   - The realized volatility for the 3-month period is derived using the standard deviation of the log returns, scaled by the square root of the typical number of trading days in a year (252).

2. **Implied Volatility (IV):**
   - Using SPY options data, the average implied volatility for both calls and puts is calculated, providing insight into the market's expectations.

3. **Variance Swap Payout:**
   - The realized variance is determined by squaring the realized volatility.
   - The variance swap payout is computed as: \( \text{Notional} \times (\text{Realized Variance} - \text{Vol Strike}^2) \).

4. **Vega Exposure Analysis:**
   - The Vega exposure for the variance swap is determined.
   - A broker's offer is taken into account: a strip of 6-month $SPX options one vol point under theo for $1M of Vega notional.
   - The Vega from the broker's trade is ascertained using the previously calculated implied volatility.
   - The overall Vega exposure after accounting for the broker's trade is calculated.

## Visualizations

- A plot of the SPY prices over the period to visualize market movements.
- A bar chart representing the Vega exposures: initial, from the broker's trade, and the total after the trade.
- A bar chart displaying the variance swap payout.

## Conclusion

The analysis suggests that while the broker's trade is beneficial in reducing the Vega exposure, there remains a significant Vega exposure even after this trade. This implies that further hedging strategies or trades may be necessary to effectively manage the associated risk.

