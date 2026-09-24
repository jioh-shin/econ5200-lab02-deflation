Index Integrity — Deflation, Substitution Bias & Goodhart
Objective
To develop and validate a reproducible economic data analysis pipeline that ensures accurate inflation adjustment, quantifies substitution bias in consumer price indices, and identifies potential distortions in performance metrics.

Methodology
Deflation Pipeline: Diagnosed and corrected four bugs in a nominal-to-real conversion function, including an incorrect base-year adjustment that mislabeled values expressed in 1982–84 dollars as 2020 dollars.

Substitution Bias: Compared the Consumer Price Index for All Urban Consumers (CPI-U) with the Chained Consumer Price Index (C-CPI-U) to estimate upper-level substitution bias. Calculated average annual inflation rates using compound growth and expressed the difference in percentage points per year.

Goodhart's Law: Examined the relationship between DAU/MAU and time per session across organic and gaming phases. Used correlation analysis to identify whether improvements in the primary performance metric coincided with deterioration in the counter-metric.

Reusable Python Module: Developed deflation_utils.py, incorporating a tested deflate_series() function for converting nominal time series into constant-dollar values.

Interactive Monitoring: Built an interactive index-integrity monitor with configurable CPI series, start dates, rolling correlation windows, and alerts for negative correlations.

Key Findings
1. Accurate Inflation Adjustment

The corrected deflation pipeline converts nominal wages into constant 2020 dollars using the average CPI for the base year. It aligns observations across both input series and excludes missing values.

2. Upper-Level Substitution Bias

The analysis identifies differences in measured inflation between CPI-U and C-CPI-U, reflecting the effects of consumer substitution across expenditure categories.

CPI-U average annual inflation: 2.61%
C-CPI-U average annual inflation: 2.35%
Estimated substitution bias: 0.27 percentage points per year
Average index-level divergence: 13.30 index points per year
The distinction between index-point changes and percentage-point differences in inflation rates is essential for interpreting price-index measurement accurately.

3. Goodhart's Law and Metric Integrity

The correlation between DAU/MAU and time per session changed from +0.93 during the organic phase to -0.96 during the gaming phase.

This sign reversal illustrates how optimizing a primary performance metric can become disconnected from the underlying objective it is intended to measure.

4. Reproducible Economic Analysis

The resulting Python module and interactive monitor provide reusable tools for inflation adjustment, price-index comparison, and early detection of potential performance-metric distortions.

