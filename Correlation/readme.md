# Correlation, Covariance, and Analytics in Decision Making and Risk/Uncertainty Mitigation.

## 1. Correlation and Covariance
### Introduction and definitions

Applying correlation and covariance in probability distributions can help assess Risk, optimize operations, and enhance predictive models. Both concepts quantify the relationship between data variables, allowing for the alteration, addition, or selection of variables for predictive modeling. In businesses, these measures enable more informed decisions, reduce uncertainties, and improve overall efficiency. For instance, understanding the correlation between assets in finance can lead to better portfolio diversification and risk management. It can result in more efficient resource allocation and demand forecasting in operations. Furthermore, in machine learning, recognizing these relationships aids feature selection and improves model accuracy.
Correlation is a statistical measure that describes the extent to which two variables are linearly related. It quantifies the degree to which a change in one variable is associated with a change in another variable. The correlation coefficient ranges from -1 to 1, where:
	1 indicates a perfect positive linear relationship: As one variable increases, the other also increases proportionally.
	-1 indicates a perfect negative linear relationship: As one variable increases, the other decreases proportionally.
	0 indicates no linear relationship: One variable has no predictable change as the other variable changes.
 
The formula for the correlation coefficient (Pearson correlation) between two variables, X and Y, is:

corr(X,Y) = (cov(X,Y)) / (σX * σY)

Where:

cov(X, Y) = 1/(n-1) * Σ(i=1 to n) [(Xi - μX)(Yi - μY)]

	σX is the standard deviation of X.
	σY is the standard deviation of Y.

## Covariance 
indicates the extent to which two random variables change together. It provides insight into the direction of the linear relationship between variables. Unlike correlation, covariance does not standardize the measure, so its magnitude depends on the scale of the variables.
	A positive value indicates that the variables tend to move in the same direction.
	A negative value indicates that the variables tend to move in opposite directions.
	A value close to zero indicates a weak or no linear relationship between the variables
The covariance between two variables, X and Y, measures how much the two variables change together. The formula for the covariance is:

cov(X, Y) = 1/(n-1) * ∑(i=1 to n) [(Xi - μX)(Yi - μY)]

Where:
- \( X_i \) and \( Y_i \) are the individual sample points indexed with \( i \).
- \( μX \) is the mean of the \( X \) values.
- \( μY\) is the mean of the \( Y \) values.
- \( n \) is the number of data points.

## Code_1: Correlation and Covariance matrices.

### Problem Statement: 
Create a data frame 'df' with monthly data for four assets (Asset_A, Asset_B, Asset_C, and Asset_D) with values between 0.005 and 0.01. The goal is to analyze the strength and linearity between these assets, calculate aggregated risk using empirical distribution, and assess correlation to gain insights into the co-behavior of these random quantities.

### Steps:
#### Data Frame Creation:
Generate a data frame with monthly data for the four assets.
Ensure that the values for each asset are between 0.01 and 0.005.
#### Correlation Matrix:
Compute the correlation matrix to understand the linear relationships and their strengths between the assets.
#### Covariance Matrix:
Compute the covariance matrix to understand how the assets change together and the direction of their relationships.

#### Summary and Results from Code_1:
The covariance matrix indicates weak linearity or relationship between the three assets.
The correlation matrix indicates the direction and strength of the linear relationships between the assets:

	Asset_A and Asset_B: positive correlation 0.9
 
	Asset_A and Asset_C: negative correlation -1
 
	Asset_B and Asset_C: negative correlation
 
	Asset_A and Asset_D: no correlation, weak correlation
 
 Correlation values are standardized, ranging from -1 to 1, allowing for comparison regardless of the scale of the original data. On the other hand, covariance values are not standardized, and their magnitude depends on the scale of the variables.
 
## Code_2:  Applying Correlation and Covariance Factors to Guide Decision-Making and Assess Risk and Uncertainty When Creating a Portfolio Model of Stocks to Optimize Returns.

Using correlation and analytics to inform investment decisions for portfolio stocks better is a strategic approach. Leveraging one year of historical data of the aggregated return downloaded from Yahoo Finance for NVIDIA, DJT (Trump Media & Technology Group Corp), GPRO, and AAPL (Apple Inc) allows for a comprehensive analysis. This data diversity enables insights into the interplay between different assets, facilitating optimized portfolio composition and risk management strategies.
 
### a. Datasets Attributes:  
Detailed in python code_2.

datasets report monthly returns of year: Year: 2023-06-21 to 2024-06-20

• Open: The opening price of the stock each day. 

• High: The highest price of the stock during the trading day.

• Low: The lowest price of the stock during the trading day.

• Close: The closing price of the stock.

• Adj Close: The adjusted closing price of the stock.

• Volume: The trading volume of the stock.

However, to build a model to optimize investment returns, we must work with the induced empirical distribution that monthly returns allow us to create.

Monthly return refers to the percentage change in a stock's price over a month. It is calculated as the difference between the closing price at the end of the Month and the closing price at the beginning of each Month, divided by the opening price, and expressed as a percentage. This metric is crucial for analyzing and understanding the performance of investments over time, providing valuable insights into price movements and trends.

$$
\text{Monthly Returns} = \frac{\text{Closing Price at end of Month} - \text{Closing Price at beginning of Month}}{\text{Opening Price}} \times 100
$$

The results of Monthly Returns are shown in Code_2.
### b. Applying Probability Distribution to Average Data Sets
Before applying probability distributions to average data sets to achieve good returns, it is essential to identify the appropriate statistics to determine which stock offers better returns.

#### Relevant Statistics for Investment and Good Returns
To make informed investment decisions, consider the following statistics:
#### -  Expected Return (Mean): This statistic helps identify which stock will likely provide better average returns.
#### -  Risk (Standard Deviation): The standard deviation of the returns captures the volatility and Risk associated with each stock.
If we treat the monthly returns of each stock as a random variable, we can use the following statistics:
#### - Expected Return: This is the mean of the monthly returns.
#### - Risk: This is the standard deviation of the monthly returns.
These statistics clearly understand each stock's potential returns and risks, enabling better investment decisions.

### c.Summary of Statistics for Monthly Returns as Random Variables
#### Expected Return (Mean): 
Indicates the average return expected from the stock.
#### Risk (Standard Deviation): 
Measures the volatility and Risk associated with the stock's returns.
#### The Coefficient of Variation (CV): 
provides a sense of relative risk; it does not address how two variables move about each other, which is what correlation measures. To fully capture the relative Risk and the relationship between variables, we need to use both the Coefficient of Variation and correlation coefficients.

CV = std/mean

|                         | NVIDIA | DJT   | GoPro | AAPL  |
|-------------------------|--------|-------|-------|-------|
| Expected Return (%)     | 9.66   | 11.35 | -7.08 | 1.21  |
| Risk (STD) (%)          | 13.17  | 39.37 | 16.90 | 6.67  |
| Coefficient of Variation| 1.36   | 3.47  | -2.39 | 5.51  |
 
#### . High return stock: DJT and NVIDIA stocks.
#### . Low-risk stock: AAPL
#### . GPRO has low-return and high-risk stocks.

When considering investing in a single stock, NVIDIA stands out as the best option due to its high return and relatively lower Risk. For risk-averse investors, AAPL is a suitable choice despite its lower return. DJT, although offering the highest return, comes with significant Risk, making it a less attractive option than NVIDIA. GPRO should be avoided due to its poor performance metrics.
#### d.Pair-wise correlation among stocks.
|       | NVIDIA | DJT   | GPRO  | AAPL  |
|-------|--------|-------|-------|-------|
| NVIDIA| 1      | 0.35  | 0.11  | 0.38  |
| DJT   |        | 1     | 0.10  | -0.36 |
| GPRO  |        |       | 1     | 0.49  |
| AAPL  |        |       |       | 1     |

Calculation detailed in Code_2


#### e. Using Correlation and Covariance to Inform Decisions on Going Beyond Investing in a Single Stock, mitigating Risk, and optimizing investment in a Portfolio of Stocks.

We analyze different cases to understand the Portfolio's output dynamics better.
#### Case_1: 
analyzing two positively correlated stocks, with and without correlation.
#### Case_2: 
analyzing two negatively correlated stocks, with and without correlation.

### Case_1: investing in two stocks, NVIDIA and DJT.
#### without correlation, X and Y are independent.

The Model will have four components:
##### . Random variable X: random Monthly returns of NVIDIA.
X = {X1 + X2 + X3…+Xn}, n = 12 months.
###### . Random variable Y: random Monthly returns of DJT.
 
Y = {Y1 + Y2 + Y3… Yn}, n= 12 months.

##### . m:  the fraction of money allocated to NVIDIA stocks(invested).
 
We want to invest m = $ 0.5, in each stock..

##### . Random variable Z: output of the Model. It captures the returns from the Portfolio.
 
The Model will allow us to capture how Z behaves.

In other words, computing the expected returns (mean) and the Risk (standard deviation) of the 
Portfolio.

Z = 0.5(X) + (0.5) Y

What are Z's statistics in that case?

#### Case 1: Correlation = 0
##### Expected Return (E(Z))
Given:

	. Expected return of NVIDIA (E(X)) = 9.66%
 
	. Expected return of DJT (E(Y)) = 11.35%
 
E(Z)=0.5×E(X)+0.5×E(Y) %

E(Z)=0.5×9.66%+0.5×11.35%  

E(Z)=4.83%+5.675% = 10.505%

So, the expected return of the portfolio E(Z) is 10.505%.

##### Standard Deviation (SD(Z))

Given:

	. Standard deviation of NVIDIA (SD(X)) = 13.17%
 
	. Standard deviation of DJT (SD(Y)) = 39.37%
 
	. Correlation (ρ) between NVIDIA and DJT = 0
 
The formula for the variance of the portfolio Z with equal weights and zero correlation is:
VAR(Z)=(0.5)2×VAR(X) + (0.5)2×VAR(Y) 
VAR(Z)=0.25×(SD(X))2 + 0.25×(SD(Y)) 2
VAR(Z)=0.25× (13.17%)2+0.25× (39.37%) 2
VAR(Z)= 0.0430
(SD(Z)) is the square root of the variance:  
SD(Z)≈20.75%

|                            | NVIDIA | DJT   | Portfolio                              |
|----------------------------|--------|-------|----------------------------------------|
| Expected Returns (mean)    | 9.66%  | 11.35%| E(Z) = (0.5) (9.66%) + (0.5) (11.35%) = 10.5% |
| Risk (std)%                | 13.17% | 39.37%| SD(Z) = sqrt((0.5)^2(13.17%)^2 + (0.5)^2 (39.37%)^2) ≈ 20.75% |
| Average Risks              | (13.17 + 39.37) / 2 = 26.27% | SD(Z) = 20.75%                         |

##### Benefits of Diversification in case of correlation =0.
	. Reduced Risk: The standard deviation of the portfolio (20.75%) is lower than the average of the individual risks (26.27%).
	. Risk Pooling Effect: Combining two assets with equal weights and zero correlation reduces the overall portfolio risk.

#### Case 2: Correlation != 0
##### 1. Positive correlation.
The correlation between NVIDIA and GJT is positive = 0.35 as calculated before.

The model output Z will be different in the case of correlated X and Y (Monthly returns of NVIDIA and GJT in a year, random variables)

Relationship formula of the two stocks including correlation and investing the same portion of money 0.5:

$$
\text{VAR(Z)} = (0.5)^2 \times \text{VAR(X)} + (0.5)^2 \times \text{VAR(Y)} + 2 \times (0.5) \times (0.5) \times \text{SD(X)} \times \text{SD(Y)} \times \text{CORR(X, Y)}
$$

As the correlation between X and Y decreases the VAR(Z) decreases, meaning that the lower the correlation, the higher the reduction in risk, in other words, the lower the correlation the lower the standard deviation.

$ 0.5 = fraction of money invested in NVIDIA

1 – 0.5 = $ 0.5 fraction of money invested in DJT

X =NVIDIA.

Y = DJT.

VAR(X) = (13.17)^2

VAR(Y) = (39.37)^2

SD(X) = 13.17

SD(Y) = 39.37

CORR(X, Y) = CORR(NVIDIA, DJT) = 0.35

VAR(Z) = (0.5)2×(13.17)2 + (0.5)2×(39.37)2 + 2 × (0.5) × (0.5) × 13.17 ×39.37 × 0.35

VAR(Z) = 521.60%

SD(Z) = 22.83%

#### Case 3: Correlation < 0
The correlation between AAPL and GJT is positive = -0.36 as calculated before.

Investing the same fraction of money($0.5) in each stock, then compare the changes in risk(standard deviation) with and without correlation(-0.36).
##### Correlation = 0
Given:

Expected return of AAPL (E(X)) = 1.21%

Expected return of DJT (E(Y)) = 11.35%

X=AAPL stock

Y = DJT stock.

E(Z)=0.5×E(X)+0.5×E(Y) %

E(Z)=0.5×1,21%+0.5×11.35%  

E(Z)= 6.28%

So, the expected return of the portfolio E(Z) is 6.28%.

##### Standard Deviation (SD(Z))

Given:

	. Standard deviation of AAPL (SD(X)) = 6.67%
	. Standard deviation of DJT (SD(Y)) = 39.37%
	. Correlation (ρ) between AAPL and DJT = 0
The formula for the variance of the portfolio Z with equal weights and zero correlation is:

VAR(Z)=(0.5)^2×VAR(X) + (0.5)^2×VAR(Y) 

VAR(Z)=0.25×(SD(X))^2 + 0.25×(SD(Y))^2

VAR(Z)=0.25× (6.28%)2+0.25× (39.37%)^2

VAR(Z)= 0.0397

(SD(Z)) is the square root of the variance:  

SD(Z)≈19.96%

##### Correlation = - 0.36
VAR(Z)=(0.5)2×VAR(X) + (0.5)^2×VAR(Y) + 2 × (0.5) × (0.5) × SD(X) ×SD(Y) × CORR(X, Y)

VAR(Z)=(0.5)^2×SD(X)2 + (0.5)2×SD(Y)2 + 2 × (0.5) × (0.5) × SD(X) ×SD(Y) × CORR(X, Y)

VAR(Z) = 0.0351

SD(Z) = 18.74

### Summary.
#### 1. Positive Correlation:
##### Effect on Risk: 
 When assets are positively correlated (ρ > 0), they tend to move in the same direction. If one asset's value increases, the other asset's value also tends to increase, and vice versa.
##### Risk Amplification: 
Positive correlation amplifies the portfolio's risk. This is because during downturns, both assets are likely to decrease in value together, leading to higher volatility and potential losses.
##### Diversification Impact: 
In a positively correlated scenario, diversification may not provide significant risk reduction since assets move in tandem, limiting the risk-reducing benefits of combining assets.
#### 2.  Negative Correlation:
##### Effect on Risk: 
Negative correlation (ρ < 0) implies that assets move in opposite directions. When one asset's value increases, the other's value tends to decrease, and vice versa.
##### Risk Reduction: 
Negative correlation can significantly reduce portfolio risk. During market fluctuations, the negative correlation helps offset losses in one asset with gains in the other, leading to a more stable portfolio.

##### Diversification Impact: 
Diversification is highly effective in a negatively correlated scenario as it leverages the opposite movements of assets to lower overall portfolio volatility and risk.
#### 3. No Correlation (Zero Correlation):

##### Effect on Risk: 
Zero correlation (ρ = 0) indicates that there is no linear relationship between the assets' movements. They move independently of each other.
#### Risk Mitigation: 
Zero correlation allows for effective risk mitigation through diversification. Assets with no correlation provide diversification benefits by spreading
 risk across uncorrelated movements.
#### Diversification Impact: 
Diversifying across uncorrelated assets can significantly reduce portfolio risk as losses in one asset may be offset by gains in another, leading to a smoother risk-return profile.

 In summary, the effect of correlation on a portfolio is profound. Positive correlation increases risk and limits diversification benefits, as assets tend to move in the same direction. Negative correlation, on the other hand, reduces risk significantly and enhances diversification benefits by offsetting movements between assets. Zero correlation allows for effective risk mitigation and maximizes diversification advantages, as movements in one asset do not affect the other. Understanding correlation is essential for constructing well-balanced and resilient investment portfolios, ensuring optimal risk management and potential for higher returns.
