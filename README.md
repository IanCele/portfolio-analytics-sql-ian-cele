# Portfolio Analysis: Institutional-Grade SQL Analytics Suite  
### by **Ian Cele, MBA — Global Commercial Strategy & AI Leader**

[![SQL](https://img.shields.io/badge/SQL-Portfolio%20Analytics-blue)](https://github.com)
[![License](https://img.shields.io/badge/License-Educational%20Use-green)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success)](https://github.com)
[![Last Updated](https://img.shields.io/badge/Last%20Updated-January%202025-informational)](CHANGELOG.md)
[![Open Source](https://img.shields.io/badge/Open%20Source-Yes-brightgreen)](https://github.com)

This repository showcases an **institutional-grade SQL analytics suite** for **multi-asset portfolio analysis**, **risk modelling**, **performance attribution**, and **evidence-backed rebalancing recommendations**.

It reflects the intersection of **commercial strategy**, **quantitative finance**, and **AI-enabled analytics**—designed and built by **Ian Cele**, a global leader in **RGMx**, **OBPPC**, and enterprise **Data/AI Transformation**.

---

# Project Overview

This project contains production-ready SQL scripts for analysing the investment portfolio of **Client #128: Ian Cele** across multiple accounts and asset classes.  
It includes:

- Advanced portfolio construction analytics  
- Multi-window risk decomposition (12M, 18M, 24M)  
- Performance attribution and correlation matrices  
- Institutional risk metrics (Sharpe, Drawdown, VaR, CVaR)  
- Data-driven rebalancing recommendations  
- PostgreSQL, MySQL, BigQuery, Snowflake compatibility  

---

# Key Deliverables

- **Client Identification** → Customer verification & account discovery  
- **Portfolio Holdings View** → Unified dimensional table with asset classifications  
- **Asset-Level Returns** → Daily, cumulative & annualised returns  
- **Risk Metrics** → Sharpe Ratio, Max Drawdown, VaR, CVaR  
- **Concentration Analysis** → Portfolio weights + HHI Index  
- **Correlation Matrix** → Co-movement & beta diagnostics  
- **Benchmarking** → Performance vs. S&P 500  
- **Rebalancing Recommendations** → Drift-based and risk-weighted  

---

# ⚙ Quick Start

## Prerequisites
- PostgreSQL 12+ (or equivalent SQL engine)  
- Access to the `invest` schema  
- Complete OHLC historical pricing data  

## Running the Analysis

```bash
# Step 1: Client Identification
psql -U user -d database -f scripts/step1-client-identification.sql

# Step 2: Create Portfolio View
psql -U user -d database -f scripts/step2-create-client-view.sql

# Step 3–6: Analytics Engine
psql -U user -d database -f scripts/step3-asset-returns.sql
psql -U user -d database -f scripts/step3-portfolio-volatility.sql
psql -U user -d database -f scripts/step3-risk-metrics.sql
psql -U user -d database -f scripts/step3-concentration.sql
psql -U user -d database -f scripts/step3-correlation.sql
psql -U user -d database -f scripts/step3-benchmark-analysis.sql

# Step 4: Portfolio Rebalancing
psql -U user -d database -f scripts/step4-rebalancing.sql
scripts/
├── step1-client-identification.sql
├── step2-create-client-view.sql
├── step3-asset-returns.sql
├── step3-portfolio-volatility.sql
├── step3-risk-metrics.sql
├── step3-concentration.sql
├── step3-correlation.sql
├── step3-benchmark-analysis.sql
└── step4-rebalancing.sql

docs/
├── TECHNICAL_NOTES.md
├── REFERENCES.md
└── DATA_PRIVACY.md

README.md
CHANGELOG.md

# Step 4: Rebalancing
psql -U user -d database -f scripts/step4-rebalancing.sql
\`\`\`

## File Structure

\`\`\`
scripts/
├── step1-client-identification.sql         # Customer verification & holdings discovery
├── step2-create-client-view.sql            # Unified portfolio view (ian_cele_view)
├── step3-asset-returns.sql                 # Asset-level return calculations
├── step3-portfolio-volatility.sql          # Portfolio return & volatility metrics
├── step3-risk-metrics.sql                  # Advanced risk (Sharpe, VaR, drawdown)
├── step3-concentration.sql                 # Weight & concentration analysis
├── step3-correlation.sql                   # Correlation matrix & risk contribution
├── step3-benchmark-analysis.sql            # Beta & S&P 500 comparison
└── step4-rebalancing.sql                   # Rebalancing recommendations

docs/
├── TECHNICAL_NOTES.md                      # SQL engineering & financial methodology
├── REFERENCES.md                           # Academic citations (Harvard & APA)
└── DATA_PRIVACY.md                         # Data handling & anonymization

README.md                                   # This file
CHANGELOG.md                                # Version history & release notes
\`\`\`

## Analysis Output Examples

### Customer Verification
Returns customer ID, name, email, phone, address, and account creation date.

### Account Summary
Displays all customer accounts with:
- Account type and status
- Number of holdings
- Total account value
- Opening date

### Holdings Joined Table
Complete investment inventory with:
- Ticker, asset name, classification (major/minor)
- Quantity, cost basis, acquisition date
- Latest price, OHLC data, volume
- Current market value
- Unrealized gain/loss ($ and %)

### Portfolio Metrics (12M/18M/24M windows)

**Returns & Volatility**
- Daily portfolio return
- Annualized return
- Annualized volatility (standard deviation)

**Risk Metrics**
- Sharpe Ratio (risk-adjusted return)
- Maximum Drawdown (peak-to-trough decline)
- Value at Risk (VaR) – 95th percentile
- Conditional VaR (expected loss beyond VaR)

**Concentration**
- Individual asset weights
- Herfindahl–Hirschman Index (HHI)
- Diversification score

**Correlation Analysis**
- Asset-to-asset correlations
- Risk contribution by asset
- Benchmark beta

## SQL Highlights

### Idempotent Design
All scripts use `CREATE OR REPLACE` for safe re-execution.

### Window Functions for Time Series
- `LAG()` for computing returns
- `SUM() OVER` for cumulative metrics
- `STDDEV()` for rolling volatility

### Star Schema Alignment
Follows dimensional modeling best practices (Kimball & Ross 2013).

### Cross-Dialect Support
Scripts are available in:
- ANSI SQL (PostgreSQL, MySQL)
- BigQuery SQL
- Snowflake SQL
- dbt Templated

## Financial Methodology

This analysis implements industry-standard portfolio theory (Markowitz 1952; Sharpe 1964) and risk modeling used by institutional asset managers:

- **CAGR**: Compound Annual Growth Rate for long-term returns
- **Sharpe Ratio**: Risk-adjusted performance vs. risk-free rate
- **Maximum Drawdown**: Worst-case historical loss from peak
- **Value at Risk (VaR)**: Expected loss at 95th percentile (historical method)
- **Conditional VaR (CVaR)**: Average loss beyond VaR threshold
- **HHI Index**: Market concentration metric (0 = diversified, 1 = concentrated)

## Rebalancing Logic

Recommendations based on:
- Current vs. target allocation drift (±5% thresholds)
- Risk-weighted optimization
- Asset-class constraints
- Tax-loss harvesting opportunities

## How to Cite This Repository

If you use this project in academic work, professional reporting, or other contexts, please cite it as follows:

### APA Format
\`\`\`
Cele, I. (2025). Portfolio analysis: SQL analytics suite for institutional investment analysis 
[Computer software]. Available at https://github.com/[username]/sql-portfolio-analysis
\`\`\`

### Harvard Format
\`\`\`
Cele, I., 2025. Portfolio analysis: SQL analytics suite for institutional investment analysis. 
Available at: https://github.com/[username]/sql-portfolio-analysis [Accessed 14 November 2025].
\`\`\`

### BibTeX
```bibtex
@software{cele2025portfolio,
  author = {Cele, Ian},
  title = {Portfolio Analysis: {SQL} Analytics Suite for Institutional Investment Analysis},
  year = {2025},
  url = {https://github.com/[username]/sql-portfolio-analysis}
}

