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

## Data Sources & Assumptions

### Home Prices (per Dublin postal district)
- **Source:** CSO Residential Property Price Index and MyHome.ie property price register (Q4 2024 / Q1 2025 asking and sale prices by Eircode routing key)
- Prices represent approximate medians for a 2-3 bed property in each area
- Commuter belt figures (Kildare, Meath, Wicklow) based on CSO county-level medians

### Rental Data
- **Source:** Daft.ie Rental Price Report (Q4 2024) and RTB Rent Index
- Monthly rents represent average asking rents for a 2-bed apartment/house in each area

### Mortgage Rates
- **Default 4.0%** reflects typical Irish fixed-rate offerings in early 2025
- **Source:** BPFI / Central Bank of Ireland Retail Interest Rate Statistics; comparison sites (Bonkers.ie, CCPC mortgage comparisons)

### Deposit (10%)
- Central Bank of Ireland macroprudential rules: minimum 10% deposit for first-time buyers (90% LTV limit)
- **Source:** [Central Bank Mortgage Measures](https://www.centralbank.ie/financial-system/financial-stability/macro-prudential-policy/mortgage-measures)

### Local Property Tax (LPT) — 0.10%
- Based on the revised LPT bands effective from 2022, with a basic rate of 0.1029% on properties valued up to €1.05M
- **Source:** [Revenue.ie — Local Property Tax](https://www.revenue.ie/en/property/local-property-tax/index.aspx)

### Stamp Duty — 1%
- 1% on residential properties up to €1M, 2% on the balance above €1M
- **Source:** [Revenue.ie — Stamp Duty on Property](https://www.revenue.ie/en/property/stamp-duty/index.aspx)

### Capital Gains Tax — 33%
- Standard Irish CGT rate on investment gains, applied to the renter's portfolio at the end of the simulation
- First €1,270 annual exemption not modelled (conservative for renter)
- **Source:** [Revenue.ie — Capital Gains Tax](https://www.revenue.ie/en/gains-gifts-and-inheritance/cgt/index.aspx)

### Home Appreciation — 3.5% mean
- Long-run Irish residential property appreciation broadly 3-4% nominal
- **Source:** CSO Residential Property Price Index (long-run trend); Central Bank Financial Stability Reviews

### Rent Growth — 4.0% mean
- Dublin rents have grown 4-6% annually over the past decade, with RPZ caps of 2% (now linked to HICP or 2%)
- 4% chosen as a moderate long-run assumption
- **Source:** RTB Rent Index; Daft.ie Rental Reports

### Investment Returns — 7.0% mean
- Approximate long-run nominal return of a globally diversified equity portfolio
- Volatility modelled at σ=16%, consistent with historical equity market standard deviation
- **Source:** Standard assumption based on long-run MSCI World / S&P 500 returns

### Legal Fees — €3,000
- Typical solicitor fees for a residential property purchase in Ireland
- **Source:** CCPC guide to buying a home; Law Society recommended ranges

### Simulation Volatility
| Variable | Mean | Std Dev (σ) | Rationale |
|----------|------|-------------|-----------|
| Home appreciation | User-set (3.5%) | 6% | Captures boom/bust cycles in Irish property |
| Rent growth | User-set (4.0%) | 2% | Lower variance due to RPZ regulation |
| Investment returns | User-set (7.0%) | 16% | Standard equity market volatility |

## Tech

Single HTML file, no build step. Only external dependency is [Chart.js](https://www.chartjs.org/) via CDN.

## Disclaimer

For educational purposes only. Not financial advice. Consult a qualified financial advisor before making property decisions.
