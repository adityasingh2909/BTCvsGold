# Bitcoin vs. Gold: Inflation Hedge & Volatility Analysis (2012-2026)

## 📌 Project Overview
This project performs a comparative econometric analysis of **Bitcoin (BTC)** and **Gold** to determine their efficacy as investment assets and inflation hedges. 

Using data from **January 2012 to January 2026**, the study applies **GARCH(1,1)** and **DCC-GARCH** models to analyze volatility persistence, risk-adjusted returns, and dynamic correlations during different inflation regimes.

> **Key Finding:** While Bitcoin offers significantly higher returns, its risk-adjusted performance (Sharpe Ratio) is nearly identical to Gold. However, the hypothesis that Bitcoin acts as an inflation hedge is **rejected** based on drawdown analysis during high-inflation periods.

---

## 📊 Key Results (2012-2026)

### 1. Performance Metrics
| Metric | Bitcoin | Gold | Analysis |
| :--- | :--- | :--- | :--- |
| **Annualized Return** | **34.4%** | 5.9% | BTC vastly outperforms in raw growth. |
| **Annualized Volatility** | 88.2% | 14.6% | BTC is approx. 6x more volatile than Gold. |
| **Sharpe Ratio** | **0.391** | **0.405** | **Identical Efficiency:** Investors are compensated equally per unit of risk for both assets. |
| **Volatility Persistence** | 0.999 | 0.999 | Volatility clusters heavily in both assets (shocks last a long time). |

### 2. Correlation & Diversification
* **Average Correlation:** `-0.0092` (Effectively Zero)
* **Implication:** Bitcoin and Gold are uncorrelated. Adding BTC to a portfolio provides genuine diversification benefits, unrelated to Gold's movements.

### 3. Inflation Hedge Analysis (Regime Testing)
The study isolated months where Eurozone Inflation (HICP) exceeded **3%**.
* **Gold Max Drawdown during High Inflation:** `-16.6%`
* **Bitcoin Max Drawdown during High Inflation:** `-87.7%`
* **Conclusion:** Bitcoin failed to act as a "store of value" during high-inflation regimes in this sample period.

---

## ⚙️ Methodology

### Data Sources
* **Bitcoin:** Monthly aggregated price data (Post-2012 filter applied to remove early "Genesis" volatility).
* **Gold:** Spot price historical data.
* **Inflation:** Eurozone Harmonised Index of Consumer Prices (HICP), including forecasts through 2026.

### Econometric Models
The analysis uses the **R** programming language with the following approach:
1.  **Log Returns:** Calculated on monthly aggregated data.
2.  **GARCH(1,1):** Used with a Student-t distribution to model time-varying volatility and "fat tails."
3.  **DCC-GARCH:** (Dynamic Conditional Correlation) used to track how the correlation between BTC and Gold evolves over time.

---

## 📦 Libraries & Dependencies

To run this analysis, ensure you have **R (v4.5+)** installed along with the following packages:

```r
install.packages(c("tidyverse", "lubridate", "rugarch", "rmgarch", "xts", "PerformanceAnalytics", "quantmod"))
💡 Executive Summary & Conclusion
This study applied DCC-GARCH modeling to determine if Bitcoin acts as a "digital gold" or safe-haven asset during periods of market stress. The results firmly reject the "Store of Value" hypothesis for the 2012-2026 period.

1. Bitcoin is a Risk Asset, Not a Safe Haven
As illustrated in the Drawdown Analysis chart, Bitcoin's risk profile is fundamentally different from Gold's. During the high-inflation regimes tested (Eurozone HICP > 3%), Gold maintained its value with a maximum drawdown of just -16.6%. In contrast, Bitcoin suffered a catastrophic -87.7% drawdown during the same inflationary pressure. This effectively disqualifies Bitcoin as a hedge against systemic currency devaluation in this sample.

2. The Efficiency Paradox
Despite the extreme volatility (approx. 6x that of Gold), Bitcoin's Sharpe Ratio (0.39) is nearly identical to Gold's (0.40). This indicates that while Bitcoin is dangerous, the market efficiently compensates investors for that risk. It is not a "gambling" asset, but rather a highly efficient, high-beta technology play.

3. Portfolio Implications
The Dynamic Conditional Correlation (DCC) model reveals that the correlation between BTC and Gold fluctuates around a mean of -0.009, effectively zero. This suggests that while Bitcoin fails as a hedge, it succeeds as a diversifier. Its price movements are idiosyncratic and uncorrelated to traditional commodities, making it a valuable addition to a multi-asset portfolio for risk dilution—provided position sizing is small.
.
