# Financial Returns & US Industrial Production: Stata Analysis

**Summary:**  
This project contains two main analyses performed in Stata:
1. Financial returns of Microsoft (MSFT) and S&P 500
2. US industrial production time series (seasonal and trend analysis)

---

## Part 1: Microsoft & S&P 500 Return Analysis

- **Simple and Log Returns:**  
  - Calculated and compared simple returns and log returns for MSFT and S&P 500.
  - Both metrics track closely, though simple returns show slightly higher peaks.

- **Monthly & Annual Estimates:**  
  - Computed expected log returns and volatilities for both assets.
  - Annualized volatility using: `Annual volatility = monthly volatility * sqrt(12)`.

- **Confidence Intervals:**  
  - 95% CIs for log returns include zero; cannot reject the null hypothesis that mean returns are zero at 5% significance level.

- **Skewness & Kurtosis:**  
  - Both distributions are negatively skewed (most observations below the median).
  - Positive kurtosis indicates fat tails and more extreme values than a normal distribution.

- **Normality & Autocorrelation:**  
  - JB (Jarque-Bera) test rejects normality for both skewness and kurtosis.
  - Significant negative autocorrelation found for lag 1; returns tend to reverse between periods.

- **Regression & Correlation:**  
  - Time-based regressions for both assets yield low R² and insignificant coefficients—poor for prediction.
  - Regression of MSFT log returns on S&P 500 shows significant correlation (R² ≈ 0.37), but low explanatory power.
  - Correlation estimate between MSFT and S&P 500 log returns is 0.61, statistically significant.

---

## Part 2: US Industrial Production Time Series Analysis

- **Seasonal Adjustment:**  
  - Compared seasonally and non-seasonally adjusted series; seasonal adjustment dampens volatility.

- **Trend & Regression:**  
  - Log transformation improves model fit (R² increases from ~0.9 to ~0.96).
  - Post-1950 log series follows a straight line, pre-1950 shows more volatility due to historical events.

- **Residuals & Autocorrelation:**  
  - Residuals of log model show autocorrelation (especially in the 1930-1940 period).
  - Correlogram reveals strong autocorrelation up to lag 38—growth periods tend to persist.

- **Seasonal Component:**  
  - Correlogram of residual differences shows cyclical/seasonal patterns (peaks at 12-month intervals).
  - Regression on lagged residuals yields low R², indicating much white noise remains.
  - Deseasonalized residuals post-1960 resemble white noise; pre-1960 is more volatile and cyclical.

- **Autocorrelation After Deseasonalization:**  
  - Autocorrelation persists, especially at annual intervals, indicating incomplete removal of seasonal effects.

---

**How to run:**  
- Open `.do` files in Stata and run them with the respective `.xlsx` data files in the same folder.

---

**Files Included:**
- `returns_analysis.do`: Stata code for MSFT & S&P 500 returns analysis
- `industrial_production.do`: Stata code for time series analysis
- `msft_sp500_data.xlsx`: Data for returns analysis
- `us_industrial_production.xlsx`: Data for production analysis
- `report.md`: Project summary and results (this file)

---
