# Introduction.
Mitigating uncertainty and risk using probability distributions
Introduction
Probability distributions are employed in predictive and prescriptive models to model and quantify uncertainty and risk, informing decision-making by capturing each possible value's relative likelihood or frequency within a given range. There are two main types of distributions used to create probability distributions:

- Empirical Distributions: These are based on experts' assessments, historical data, or data generated from observations. They reflect the actual distribution of the data as observed in practice.
 
- Standard Probability Distributions refer to theoretical models of empirical distributions with well-defined statistical properties. Examples include the normal distribution, binomial distribution, and Poisson distribution. These distributions serve as foundational models in statistical analysis and probability theory, providing a framework for understanding the behavior of random variables and enabling the calculation of probabilities and critical values. They can be applied to model real-world phenomena, even with small sample sizes accurately. Employing these distributions in models helps capture the underlying uncertainty and variability in data, allowing for more informed and reliable decision-making.
## Probability Distribution Function (PDF)
The probability distribution function refers to the probability density function (for continuous variables) or the probability mass function (for discrete variables).

The Probability Density Function, denoted as f(x), describes the likelihood of the random variable taking on a particular value. However, the probability at any specific point is zero; the PDF determines the probability over an interval.
  ### Properties and usage.
- f(x) ≥ 0 for all x. nonnegative.
- The integral of the PDF over the entire range of the random variable equals one:
  
$$\int_{-\infty}^{\infty} f(x) \, dx = 1$$
    
- The probability that the random variable X falls within a certain interval [a,b] is given by the integral of the PDF over that interval: 

$$P(a \leq X \leq b) = \int_{a}^{b} f(x)dx$$

## Probability Mass Function (PMF)
The PMF, denoted as P(X=x), gives the probability that a discrete random variable X exactly equals some value x.
### Properties and usage.
- P(X=x) ≥ 0 for all x.
- The sum of the PMF over all possible values of the random variable equals one:
$$\sum_{x} P(X = x) = 1$$
- The PMF directly gives the probability of each possible value of the discrete random variable.
## Cumulative Distribution Function (CDF)
The CDF can be used for both types of random variables (discrete and continuous).
The CDF, denoted as F(x), gives the probability that the random variable X takes on a value less than or equal to x: 
$$F(x) = P(X \leq x)$$
### Properties and usage:
- The CDF is non-decreasing, meaning
  $$F(x) \leq F(y) \text{ for } x \leq y$$
- The CDF approaches 0 as x approaches negative infinity and approaches one as x approaches positive infinity: 
$$\lim_{x \to -\infty} F(x) = 0 \quad \text{and} \quad \lim_{x \to \infty} F(x) = 1$$

The CDF provides the probability that a random variable is less than or equal to a specific value. 
- For continuous random variables, it is the integral of the PDF up to x:
$$F(x) = \int_{-\infty}^{x} f(t) \, dt$$
- For discrete random variables, it is the sum of the PMF up to x:
$$F(x) = \sum_{t \leq x} P(X = t)$$
## Empirical Cumulative Distribution Function (ECDF)
ECDF is used to  create a model to predict future data metrics with unknown probability distribution aggregated risk.

The ECDF is calculated by ordering all the unique observations in the data sample and calculating the cumulative probability for each as the number of observations less than or equal to a given observation divided by the total number of observations.
$$\text{ECDF}(X) = \frac{1}{n} \sum_{i=1}^{n} 1\{X_i \leq x\}$$
{Xi≤x} is 1 if X<=x otherwise 0.

The Empirical Cumulative Distribution Function (ECDF) is a data-driven estimator of the Cumulative Distribution Function (CDF) constructed from observed data with unknown distribution. It provides a non-parametric estimate of the cumulative distribution function, meaning it does not assume any specific underlying distribution for the data. The ECDF serves several important purposes:
- Empirical Measure: It empirically measures the proportion of data points less than or equal to a given value x.
- Visualization: It is useful for visualizing the distribution of a sample without making any parametric assumptions. This makes the ECDF a powerful tool for exploratory data analysis, as it allows for examining the data's distribution in a straightforward and assumption-free manner.
- Comparison: The ECDF can be compared with theoretical CDFs to assess goodness-of-fit. By comparing the ECDF to a theoretical CDF, one can evaluate how well a chosen theoretical distribution matches the observed data. This is often done using statistical tests such as the Kolmogorov-Smirnov test.

The ECDF is particularly valuable in contexts where the underlying distribution is unknown or complex, providing a flexible and intuitive approach to understanding the distributional properties of a sample.
# Python Examples.
## Example_1: applying Probability Distribution Function on discrete random variables (normal distribution)
Consider a construction manager who oversees a team of workers. The daily workload includes managing tasks for 20 workers per day. Unfortunately, due to absenteeism, about 20% of workers fail to show up for work, leading to project delays and increased costs for the construction company.
### Objective:
- Find the ideal number of workers the manager should schedule daily to ensure the project stays on track, assuming only 80% of the planned workers show up.
- Use Python to intuitively calculate how many workers the construction manager should schedule to ensure that, on average, 20 workers are available daily.
- Find the cumulative density function to statistically calculate how many workers (in percent) the manager will schedule d if we use the linear calculations from the first step to schedule workers.
- Use the binomial pdf () function to determine the number of workers the manager should schedule to limit the risk of having more than 20 workers per day to 5%.

* Results are shown on Code_1.py
## Example_2:  Applying ECDF
Create a non-normally distributed dataset by combining two normal distributions to form a bimodal distribution. After generating the dataset, calculate and plot the Empirical Cumulative Distribution Function (ECDF). This process involves merging data points from two distinct normal distributions, ensuring that the resulting dataset exhibits two peaks characteristic of a bimodal distribution. Subsequently, the ECDF will be used to visualize the cumulative probabilities associated with the dataset, providing a comprehensive view of its distributional properties. Additionally, calculate the statistics of the ECDF to find new probability values, which will help in understanding the distribution's behavior and in making informed decisions based on the dataset* Results are shown on code_2.py
