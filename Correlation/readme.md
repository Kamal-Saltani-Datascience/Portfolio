
# Correlation, Covariance, and Analytics in Decision Making

## Introduction

Applying correlation and covariance in probability distributions can help assess risk, optimize operations, and enhance predictive models. Both concepts quantify the relationship between data variables, allowing for the alteration, addition, or selection of variables for predictive modeling. In businesses, these measures enable more informed decisions, reduce uncertainties, and improve overall efficiency. For instance, understanding the correlation between assets in finance can lead to better portfolio diversification and risk management. It can result in more efficient resource allocation and demand forecasting in operations. Furthermore, in machine learning, recognizing these relationships aids feature selection and improves model accuracy.

## Correlation

Correlation is a statistical measure that describes the extent to which two variables are linearly related. It quantifies the degree to which a change in one variable is associated with a change in another variable. The correlation coefficient ranges from -1 to 1, where:

- **1** indicates a perfect positive linear relationship: As one variable increases, the other also increases proportionally.
- **-1** indicates a perfect negative linear relationship: As one variable increases, the other decreases proportionally.
- **0** indicates no linear relationship: One variable has no predictable change as the other variable changes.

The formula for the correlation coefficient (Pearson correlation) between two variables, X and Y, is:

\[ \text{corr}(X, Y) = \frac{\text{cov}(X, Y)}{\sigma_X \sigma_Y} \]

Where:

- \(\text{cov}(X, Y)\) is the covariance between X and Y.
- \(\sigma_X\) is the standard deviation of X.
- \(\sigma_Y\) is the standard deviation of Y.

## Covariance

Covariance indicates the extent to which two random variables change together. It provides insight into the direction of the linear relationship between variables. Unlike correlation, covariance does not standardize the measure, so its magnitude depends on the scale of the variables.

- A positive value indicates that the variables tend to move in the same direction.
- A negative value indicates that the variables tend to move in opposite directions.
- A value close to zero indicates a weak or no linear relationship between the variables.

The formula for the covariance between two variables, X and Y, is:

\[ \text{cov}(X, Y) = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \mu_X)(Y_i - \mu_Y) \]

Where:

- \(X_i\) and \(Y_i\) are the individual sample points indexed with \(i\).
- \(\mu_X\) is the mean of the X values.
- \(\mu_Y\) is the mean of the Y values.
- \(n\) is the number of data points.

## Code 1: Correlation and Covariance Matrices

### Problem Statement

Creating a DataFrame `df` with monthly data for four assets, Asset_A, Asset_B, Asset_C, and Asset_D, with values between 0.01 and 0.005. The goal is to analyze the strength and linearity between these assets using correlation and covariance matrices.

### Steps

1. **Data Frame Creation:**
   - Generate a data frame with monthly data for the four assets.
   - Ensure that the values for each asset are between 0.01 and 0.005.
2. **Correlation Matrix:**
   - Compute the correlation matrix to understand the linear relationships and their strengths between the assets.
3. **Covariance Matrix:**
   - Compute the covariance matrix to understand how the assets change together and the direction of their relationships.

### Summary

- The covariance matrix indicates weak linearity or relationship between the three assets.
- The correlation matrix indicates the direction and strength of the linear relationships between the assets:
  - Asset_A and Asset_B: positive correlation 0.9
  - Asset_A and Asset_C: negative correlation -1
  - Asset_B and Asset_C: negative correlation
  - Asset_A and Asset_D: no correlation, weak correlation

Correlation values are standardized, ranging from -1 to 1, allowing for comparison regardless of the scale of the original data. On the other hand, covariance values are not standardized, and their magnitude depends on the scale of the variables.

## Code 2: Utilizing Correlation and Covariance Factors

### Portfolio Selection

Using correlation and analytics to inform investment decisions for portfolio stocks better is a strategic approach. Leveraging one year of historical data of the aggregated return downloaded from Yahoo Finance for NVIDIA, DJT (Trump Media & Technology Group Corp), GPRO, and AAPL (Apple Inc) allows for a comprehensive analysis. This data diversity enables insights into the interplay between different assets, facilitating optimized portfolio composition and risk management strategies.

- **Year:** 2023-06-21 to 2024-06-20
- **Datasets Statistics:**
  - A summary of the four data's distribution and variability across different attributes such as prices (Open, High, Low, Close, Adj Close) and trading volume (Volume).

### Monthly Returns

Monthly return refers to the percentage change in a stock's price over a month. It is calculated as the difference between the closing price at the end of the month and the closing price at the beginning of the month, divided by the opening price, and expressed as a percentage. This metric is crucial for analyzing and understanding the performance of investments over time, providing valuable insights into price movements and trends.

\[ \text{Monthly Returns} = \frac{\text{Closing Price at end of Month} - \text{Closing Price at the beginning of Month}}{\text{Opening Price}} \times 100 \]

### Applying Probability Distribution to Average Data Sets

Before applying probability distributions to average data sets to achieve good returns, it is essential to identify the appropriate statistics to determine which stock offers better returns.

### Relevant Statistics for Investment and Good Returns

To make informed investment decisions, consider the following statistics:

- **Expected Return (Mean):** This statistic helps identify which stock will likely provide better average returns.
- **Risk (Standard Deviation):** The standard deviation of the returns captures the volatility and risk associated with each stock.

If we treat the monthly returns of each stock as a random variable, we can use the following statistics:

- **Expected Return:** This is the mean of the monthly returns.
- **Risk:** This is the standard deviation of the monthly returns.

### Summary of Statistics for Monthly Returns as Random Variables

- **Expected Return (Mean):** Indicates the average return expected from the stock.
- **Risk (Standard Deviation):** Measures the volatility and risk associated with the stock's returns.
- **Coefficient of Variation (CV):** Provides a sense of relative risk; it does not address how two variables move about each other, which is what correlation measures. To fully capture the relative risk and the relationship between variables, we need to use both the Coefficient of Variation and correlation coefficients.

\[ \text{CV} = \frac{\text{std}}{\text{mean}} \]

|          | NVIDIA | DJT | GoPro | AAPL |
|----------|--------|-----|-------|------|
| **Expected Return (mean) %** | 9.66 | 11.35 | -7.08 | 1.21 |
| **Risk (STD) %** | 13.17 | 39.37 | 16.90 | 6.67 |
| **Coefficient of Variation (Relative Risk)** | 1.36 | 3.47 | -2.39 | 5.51 |

If we consider investing in a single stock, we have the following options:

- **High return stock:** DJT and NVIDIA stocks.
- **Low-risk stock:** AAPL
- **GPRO:** low-return and high-risk stocks.

When considering investing in a single stock, NVIDIA stands out as the best option due to its high return and relatively lower risk. For risk-averse investors, AAPL is a suitable choice despite its lower return. DJT, although offering the highest return, comes with significant risk, making it a less attractive option than NVIDIA. GPRO should be avoided due to its poor performance metrics.

### Using Correlation and Covariance to Inform Decisions

Going beyond investing in a single stock and optimizing investment in a portfolio of stocks:

#### Pair-wise Correlation among Stocks

|          | NVIDIA | DJT | GPRO | AAPL |
|----------|--------|-----|------|------|
| **NVIDIA** | 1      | 0.35 | 0.11 | 0.38 |
| **DJT**    |        | 1    | 0.1  | -0.36 |
| **GPRO**   |        |      | 1    | 0.49 |
| **AAPL**   |        |      |      | 1    |

### Objectives

- Optimizing returns by diversifying the portfolio.
- Creating a model portfolio containing NVIDIA and DJT stocks.

### Model Inputs

- **Random variable X:** random monthly returns of NVIDIA.
- **Random variable Y:** random monthly returns of DJT.
- **m:** the fraction of money allocated to NVIDIA stocks (invested).

### Model Outputs

- **Random variable Z:** captures the returns from the portfolio.

The model will allow us to capture how Z behaves, i.e., compute the expected return and the risk of the portfolio.

\[ Z = mX + (1-m)Y \]

#### Case 1: Investing all the money in NVIDIA stocks

- X and Y are independent (no correlation).
