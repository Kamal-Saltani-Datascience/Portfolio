# Linear regression

Linear Regression is a statistical method used to model the relationship between independent input variables (regressors), typically denoted as xi, and dependent output variables(responds), typically denoted as yi .
This method creates a linear equation (or line) that best fits the observed data points, allowing us to understand how changes in the independent variable are associated with changes in the dependent variable. 
The resulting model can then be used to predict future values of the dependent variable based on new, unseen values of the independent variable. 
Linear regression can model multiple independent variables depending on the problem at hand:
	In simple linear regression, we have one independent variable related to one dependent variable.
Linear equation of simple linear regression.

y= β0 + β1x +ϵ
 Where:
y is the dependent variable, a random variable generated as the sum of three terms:
	β0 is the y-intercept, and it's a constant.
	β1  is the slope.
	x is the independent variable.
	ϵ is the error term, as we don't expect that y to be determined by x and β1; we have some uncounted stuff that the Model cannot explain, so we think about it as noise ϵ.
In the linear equation, as x changes, y changes, as long as β1 != 0.

	In multiple linear regression, we have more than one independent variable (multivariable) and one resulting dependent variable.
Linear equation of multiple linear regression.

y= β0+ β1x1+ β2x2+…+ βnxn+ ϵ
 	Where:
	y is the dependent variable.
	{x1, x2,…,xn } are the independent variables.
	{β1, β2,…,βn } are the coefficients.
	β0 is the y-intercept.
	ϵ is the error term.

In simple linear regression, the goal is to find a line that represents a model which best fits the data. This line is determined by minimizing the sum of squared errors (SSE), which measures the total deviation or residual errors of the observed values from the predicted values.
The equation for estimated simple linear regression is:
 y ̂ = b0 + b1x
	Where:
	 ( y) ̂:  Predicted or estimated value of the dependent variable y.
	  x: Independent variable (predictor)
	  b0: Intercept (constant term), which represents the predicted value of   y ̂ when x is zero and represent the unknown β0  in the linear equation model.
	  b1: Slope (coefficient), which represents the change in   y ̂ for a one-unit change in x and represent the estimated value of β1 .
	The estimated linear equation y ̂  does not need ϵ , because we are not trying to model the noise.
The coefficients  b0 and b1 are estimated using statistical methods to minimize the SSE, ensuring the line fits the data as closely as possible. This linear relationship allows us to predict  y ̂ for any given x, providing insights into how changes in x influence y.
To assess the strength of the relationship between variables, the goodness-of-fit of the model, and understanding the variability and prediction accuracy of the linear regression model, we need to evaluate the following statistics:
	Slope (b1): The coefficient that represents the change in the dependent variable  y ̂ for a one-unit change in the independent variable x.
	Intercept (b0): The constant term in the estimated regression equation, representing the estimated value of  y ̂ when x is zero.
	SST (Total Sum of Squares): The total variation in the dependent variable  y ̂ explained by the regression model.
	SSR (Regression Sum of Squares): The variation in  y explained by the regression model.
	SSE (Error Sum of Squares): The variation in  y (observed values) that is not explained by the regression model (estimated values).

SSE=∑_(i=1)^n▒(yi- y ̂  i)^2 

	Correlation: The strength and direction of the linear relationship between the independent and dependent variables.
	R-squared (Coefficient of Determination): The proportion of the variance in the dependent variable y that is predictable from the independent variable(s) x. It ranges from 0 to 1, where higher values indicate a better fit of the model.
	Standard Deviation: The measure of the dispersion or variability of the dependent variable y around the regression line.
To estimate the coefficients, intercept b0 and the slope b1 , of the linear regression model we use Ordinary Least Squares (OLS) , by minimizing SSE(Sum of squared errors).
 Code. 1: Model implementation for Simple Linear Regression.
![image](https://github.com/user-attachments/assets/e64f7b15-3d56-4509-a584-9902e826e330)

