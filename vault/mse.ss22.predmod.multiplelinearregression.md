---
id: d1gf7ejaj3q3ejp0sraf5u8
title: Multiplelinearregression
desc: ''
updated: 1646815978272
created: 1646812960677
---
# Multiple Linear Regression

Example with advertising. Sales ~ TV looks good with a $log$ transformation of the response variable.

t-statistics = coefficient / std.error

## How to make a prediction of sales given the levels of the three advertising media budgets?
Add further coefficiant

$$Y = \beta_0 + \beta_1 X_1 + \beta_2 X_2 + ... + \beta_n X_n + \epsilon$$
## Example
$$\text{sales} = \beta_0 + \beta_1 \text{TV} + \beta_2 \text{radio} + \beta_n \text{newspaper} + \epsilon \to \text{graphical representation impossible} $$


$$ \text{RSS} = \sum_{i = 1}^{n} r^2_i \to r = (y_i - \hat{\beta_1} x_{i 1} - \hat{\beta_2} x_{i 2} ...)^2 $$ 


**No statistical evidence Page 9 - Newspapers coefficiant is 0 - p value quite hight - null hypothsis can not be rejected -- Newspapers correlates with Radio or TV data**

![correlation newspapers and radio](/assets/images/2022-03-09-09-34-01.png)

Do all predictors $X_1$ to $X_n$ help to get the response variable or only a subset of them? How well does the model fit the data?

$$ E(\frac{\text{RSS}}{n - p - 1}) = \sigma^2 = E(\frac{\text{TSS} - \text{RSS}}{p}) \to \text{if the null hypothesis is true}$$
**else it would be**
$$E(\frac{\text{TSS} - \text{RSS}}{p}) > \sigma^2$$

**F statistics with a value of 570 means we can reject the null hypothesis in [[mse.ss22.predmod.mlr]]**

