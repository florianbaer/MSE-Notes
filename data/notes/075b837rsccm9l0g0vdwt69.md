# Simple linear regression
we get the 95% [[confidence interval]] with the following formula: [$\hat{\beta_1} - 2 * \text{se}(\hat{\beta_1}), \hat{\beta_1} + 2 * \text{se}(\hat{\beta_1})$]

$\epsilon = Y - (\beta_0 + \beta_1 * X)$ cannot be measured since $\beta_0$ and $\beta_1$ are unknown.

Approximation for residuals for $\epsilon$ **residuals** $r_i = y_i - (\beta_0 + \beta_1 * x_i)$

[[RSE]] Residual Standard Error = $\text{RSE} = \sqrt{\frac{r_1^2 + ... + r_n^2}{n - 2}}$

Prediction Interval = $\text{se}(y_0)^2 = \sigma^2 (1 + \frac{1}{n}+ \frac{(x_0 - \bar{x}^2)}{\Epsilon_{i = 1}^2 (x_i - \bar{x})^2})$

# Model Assumptions for the Error Term
$\epsilon_i\text{ iid }\N(0,\sigma^2)$

## Aim of residual analysis
If the model contains errors - we get a starting point for further investigation to a better and more adapted model (explorative data analysis)

**RSE** considered a measure of the **lack of fit** of a regression model to the data. 
**$R^2$** Statistic is defined as : $R^2 = 1 - \frac{\Epsilon_{i = 1}^n (y_i - \hat{y_i})^2}{\Epsilon_{i = 1}^n (y_i - \bar{y_i})^2} = 1 - \frac{\text{variance left after regression fit}}{\text{total variance}}$

$R^2$ is always between 0 and 1 (0 is bad, 1 is a perfect model)

# [[Correlation Coefficient]]
$r = Cor(X,Y) = \frac{\Epsilon_{i = 1}^n (x_i - \bar{x_i})(y_i - \bar{y_i})}{\sqrt(\Epsilon_{i = 1}^n (x_i - \hat{x_i})^2)\Epsilon_{i = 1}^n (y_i - \bar{y_i})^2)}$

You can not use the Correlation because of Multiple Linear Regression

# Diagnostics Tool for Testing Model Assumption - Tukey-Anscombe-Plot
Verify that $E[\epsilon] = 0$
## Tukey-Anscombe-Plot
Do it by the use of the **Tukey-Anscombe-Plot**

- Residuals ploted on the vertical axis
- predicted values on the horizontal axis

Values should be in a horizontal line at Residuals = 0

Simulate Points to get more points 

![](assets/images/tukey_ascom.png)

## Scale-Location Plot

Use the Standardized residuals 

### Consequences for case of correlated error terms
- The standard errors that are computed for the estimated regression coefficients or the fitted values are based on the assumption of independent error terms $\epsilon_i$
- If there is correlation among the error terms, then the estimated standard errors will tend to underestimate the true standard errors. As a result, confidence and prediction intervals will be narrower than they should be

# Outlier
An outlier is if a data point is very far away from the most of the data.
If we remove an outlier - we have a small effect on the $\beta_0$ and $\beta_1$ but the effects on the **RSE** and $R^2$ is large

## High Leverage points
![](assets/images/high_leverage_points.png)
If we remove observation 41 - the red line is the correct point - so if we remove high leverage points, the impact on $\beta_0$ and $\beta_1$ is big.

## Cooks distance
$\hat{y}_{-i}$ obeservation if you remove the i-th value.
As higher the value of cooks distance is - the higher is the influence of the i-th data point on the dataset
If a cooks value higher than 1 is observed - the value is considered as dangerously influencual.

**Read more about Tukey first aid principles**


**If you discover outliers and high leverage points - do not just remove them - it could be an important discovery for a new and other model!!!**

1. Check wether outlier has occured due to an error in data collecito or recording
   1. If an error may have occured: omit the data point
   2. if an error can be excluded: go to 2
2. Attempt to transform predictor or response variables in order to make _disappear_ the outlier. If no improvement go to 3.
3. Outlier occured due to an unusual random varianions: If such outlier affect parameter estimation too much, then the observation my be removed (**needs to be mentioned in the reports**)

