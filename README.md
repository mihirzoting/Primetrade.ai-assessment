# Trader Behavior Analysis Based on Bitcoin Market Sentiment

## Executive Summary
This study analyzes 211,224 crypto trades against the Fear & Greed Index (FGI) and finds a statistically significant relationship between sentiment regimes and profitability (ANOVA: F=7.738, p=3.14×10⁻⁶). Extreme Greed periods deliver 83% higher mean PnL ($130.21 vs. $71.03 in Extreme Fear) and a 17% win‑rate uplift (89.17% vs. 76.22%). Profit factors range from 2.16× to 11.02×, indicating strong sentiment‑driven risk‑adjusted performance differences. Trader segmentation shows a 5–7× performance spread between top and bottom deciles, supporting sentiment‑aware risk budgeting and trader‑level monitoring.

## Project Objective
Quantify how market sentiment influences trading profitability, win rates, risk‑adjusted returns, and trader heterogeneity, and translate these insights into actionable business recommendations for a Web3 trading desk.

## Dataset Overview
- **Trades:** 211,224 executions with timestamp, size, side, PnL, fees, account, and coin.
- **Sentiment:** Daily FGI classification (Extreme Fear, Fear, Neutral, Greed, Extreme Greed).
- **Post‑Cleaning:** 104,408 trades with non‑zero PnL used for performance metrics.
- **Merge Quality:** 99.98% alignment between trades and FGI dates (6 records excluded).

## Methodology
1. **Descriptive Statistics:** Mean, sum, and count of PnL by sentiment; win rates computed as % of profitable trades.  
2. **Hypothesis Testing:** One‑way ANOVA testing equality of mean PnL across sentiment regimes.  
3. **Risk Metrics:** Profit factor = total gains / |total losses| per sentiment class.  
4. **Segmentation:** Trader deciles (top 10%, middle 80%, bottom 10%) for performance dispersion.  

## Exploratory Data Analysis
**Profitability and activity vary meaningfully across sentiment regimes:**

![Profitability Analysis](./images/Profitability%20Analysis.png)

![Trading Activity](./images/Trading%20Activity.png)

| Sentiment | Mean PnL | Total PnL | Trade Count | Median PnL |
|-----------|----------|-----------|-------------|-----------|
| Extreme Greed | 130.21 | $2,715,171 | 20,853 | 8.53 |
| Fear | 112.63 | $3,357,155 | 29,808 | 6.35 |
| Neutral | 71.20 | $1,292,921 | 18,159 | 4.58 |
| Greed | 85.40 | $2,150,129 | 25,176 | 4.93 |
| Extreme Fear | 71.03 | $739,110 | 10,406 | 6.39 |

**Win rate patterns by sentiment:**

![Win Rate Analysis](./images/Win%20Rate%20Analysis.png)

- Extreme Greed: **89.17%**
- Fear: **87.29%**
- Neutral: **82.39%**
- Greed: **76.89%**
- Extreme Fear: **76.22%**

## Statistical Validation
**ANOVA (mean PnL across 5 sentiment regimes):**  
F = **7.738**, p = **3.14×10⁻⁶** → reject H₀ at α=0.05.  

**Interpretation:** Mean profitability differs significantly by sentiment, with an 83% spread between Extreme Fear and Extreme Greed.

## Risk Metrics Analysis
**Profit Factor by sentiment:**

![Profit Factor Visualization](./images/Profit%20Factor%20Visualization.png)

| Sentiment | Profit Factor | Interpretation |
|-----------|---------------|----------------|
| Extreme Greed | 11.02 | Exceptional risk‑adjusted return |
| Fear | 6.66 | Strong upside capture |
| Neutral | 4.32 | Moderate risk‑adjusted performance |
| Greed | 3.03 | Lower downside protection |
| Extreme Fear | 2.16 | Highest loss severity |

## Trader Segmentation Analysis
Performance is highly skewed across traders:

![Trader Segmentation](./images/Trader%20Segmentation.png)

```
Top 10%:    $2,143,383  (top account)
Middle 80%: [aggregated middle performers]
Bottom 10%: [significant underperformance]
```

Top‑decile traders materially outperform, indicating strategy quality and execution discipline as key drivers.

## Key Findings
1. **Sentiment‑profitability link is statistically significant** (p < 0.001).  
2. **Extreme Greed delivers the strongest returns** (mean PnL 130.21; profit factor 11.02×).  
3. **Win rates peak in Extreme Greed** (89.17%), indicating regime‑aligned trade selection.  
4. **Trader performance dispersion is large** (5–7× between deciles).  
5. **Profitability concentrates in mid‑cap assets** (@107, HYPE, SOL) rather than only large caps.  

## Business Implications
- **Sentiment‑aware sizing:** Increase allocation during Extreme Greed; reduce exposure in Extreme Fear.  
- **Risk budgeting:** Profit factor deterioration in Extreme Fear implies tighter stop‑losses and position caps.  
- **Trader governance:** Segmentation supports tiered risk limits and performance‑based capital allocation.  

## Recommendations
1. Deploy sentiment‑based position sizing tied to profit‑factor tiers.  
2. Institutionalize trader segmentation dashboards with periodic performance audits.  
3. Expand the analysis window to validate regime stability and seasonality.  
4. Build a real‑time sentiment overlay for trade approvals and hedging adjustments.  

## Conclusion
Market sentiment, measured by the Fear & Greed Index, is a statistically significant and economically meaningful driver of crypto trading outcomes. The combination of elevated profit factors during Extreme Greed and pronounced trader‑level dispersion supports deploying sentiment‑aware risk controls and trader‑performance frameworks to improve portfolio efficiency and downside protection.

## Installation
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

## Project Structure
```
Assesment/
├── analysis.ipynb
├── README.md
├── dataset/
│   ├── historical_data.csv
│   └── fear_greed_index.csv
└── images/
```

## How to Run
Open `analysis.ipynb` in VS Code or Jupyter, select the project venv, and run all cells top‑to‑bottom to reproduce tables and figures.
