# Rent vs Buy Calculator - Dublin, Ireland

A Monte Carlo simulation tool that helps you decide whether to rent or buy in Dublin.

**Live site: [stasfeelin.github.io/rent-vs-buy-dublin](https://stasfeelin.github.io/rent-vs-buy-dublin/)**

## What It Does

- Select from 25 Dublin areas (D01-D24 + commuter belt) with pre-loaded median home prices and average rents
- Runs a 30-year Monte Carlo simulation (5,000 randomised scenarios by default)
- Compares net worth of buying vs renting + investing the difference
- Shows interactive charts: wealth over time, outcome distribution, and breakeven analysis

## Ireland-Specific Parameters

| Parameter | Default | Notes |
|-----------|---------|-------|
| Deposit | 10% | Irish first-time buyer standard |
| Mortgage rate | 4.0% | Current Irish market |
| Local Property Tax | 0.10% | LPT rate for most Dublin homes |
| Stamp duty | 1% | Irish rate (up to €1M) |
| Capital Gains Tax | 33% | Applied to renter's investment gains |
| Legal fees | €3,000 | Included in buyer's upfront costs |

All parameters are adjustable. Home appreciation, rent growth, and investment returns are randomised each year across simulations to model real-world uncertainty.

## Tech

Single HTML file, no build step. Only external dependency is [Chart.js](https://www.chartjs.org/) via CDN.

## Disclaimer

For educational purposes only. Not financial advice. Consult a qualified financial advisor before making property decisions.
