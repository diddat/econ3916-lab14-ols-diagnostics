# OLS Diagnostics: When the Standard Error Is Lying

## Objective
The objective of this lab was to understand how violations of OLS regression assumptions affect coefficient estimates and standard errors, and how to identify these problems using diagnostic tests and robust standard errors.

## Methodology
- Simulated data with heteroskedasticity and compared classical standard errors with HC3 robust standard errors.
- Ran 400 simulations to compare how often classical and robust 95% confidence intervals contained the true slope.
- Analyzed four residual plots to identify heteroskedasticity, nonlinear relationships, and outliers.
- Used Breusch-Pagan and Jarque-Bera tests to examine regression assumptions.
- Measured influential observations using leverage, standardized residuals, and Cook's distance.
- Removed an influential observation and compared the regression results.
- Used the California Housing dataset to compare classical and robust standard errors.
- Created an `hc3_se()` function to calculate the HC3 robust standard error for a selected regression coefficient.

## Key Findings
- Heteroskedasticity does not necessarily bias OLS coefficients, but it can make classical standard errors unreliable.
- In the simulations, classical confidence intervals covered the true slope 91.8% of the time, compared with 93.5% for robust confidence intervals. The robust intervals were closer to the expected 95%.
- Residual plots helped identify problems that statistical tests alone might miss.
- Removing one influential observation changed the estimated slope by approximately 0.9%, while the standard error decreased by 33%. This showed that outliers can affect uncertainty estimates more than coefficients.
- In the California Housing regression, the coefficient on AveRooms was approximately -0.0273, with an HC3 standard error of 0.0121 compared with a classical standard error of 0.0024.
- After excluding the 965 districts at the housing value ceiling, the HC3 standard error on AveRooms decreased from 0.0121 to 0.0082.

## Conclusion
This lab showed me why checking regression assumptions is important before interpreting results. I learned that a coefficient can appear statistically significant because its standard error is inaccurate. Robust standard errors, residual plots, and influence measures help determine whether regression results are reliable. I also learned that removing observations just to improve results is not appropriate without a valid reason.
