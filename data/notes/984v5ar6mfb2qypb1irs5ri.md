
# Variance inflation factor (vif)

If VIF is between 5 and 10 - it will become problematic regarding collinearity

Smallest value of vif is 1


# if you want to add a squared term
```r
summary(lm(mpg ~ horsepower + I(horsepower^2), data = Auto))$r.squared
```
Add the **I** before the squred term!!!

1. plot is tukey ascom
2. normal plot
3. scale-location plot
4. cooks-distance plot
5. residuals vs leverage

# LMS2.1 shows forward 

