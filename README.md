# Citi MQA - Coffee Commodities

Notebook completed for the Citi Markets Quantitative Analysis job simulation, commodities desk. It covers the pricing and risk management of derivatives on Arabica coffee futures (ICE Coffee "C").

## Contents

1. Futures pricing: cost of carry, market-implied carry, contango and backwardation
2. Option pricing: Black-76, put-call parity and Black-Scholes cross-check, implied volatility
3. Monte Carlo: validation of the pricer, simulated paths, terminal price distribution
4. Structuring: digital options, strike selection, capital-protected note
5. Risk management: Greeks, hedging comparison (future, call, zero-cost collar), frost stress tests, 1-day VaR and CVaR

## Main results

| | |
|---|---|
| Futures fair price (6 months) | $2.7582/lb |
| Call price (K = 2.80, vol 25%) | $0.1721/lb, i.e. $6,453 per contract |
| Risk-neutral probability of exercise | 43.1% |
| Market-implied carry | 11.0% vs 1.0% assumed |
| 1-day 95% VaR, long 37 calls | $46,189 |

## Inputs

Spot from the ICO composite indicator (2026-09-09), 6-month US Treasury rate of 4.01%, storage cost of 1%, no convenience yield, volatility of 25%. The volatility is assumed rather than calibrated on the option chain.

## Running the notebook

```bash
pip install numpy pandas scipy matplotlib jupyter
jupyter notebook citi_MQA_en.ipynb
```

Tested with Python 3.11.

## Limitations

The model assumes a constant volatility and no jumps, so it ignores both the coffee skew and frost-driven price jumps. The ICO spot is a composite that includes Robusta, which explains most of the gap between the theoretical and market futures prices.

## Author

Jeremy Caillaud
