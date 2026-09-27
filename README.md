# Factors Influencing Student Academic Performance
### Multiple Linear Regression in Python and SPSS

A statistical modeling project that identifies which study habits drive student performance, with full assumption testing and cross-validation between two platforms.

Course project for Data Analytics and Statistics 2 (SM340), Financial Engineering, University of the Thai Chamber of Commerce.

## Objective

1. Build a multiple regression model explaining the Performance Index from five student behavior variables
2. Test every classical regression assumption before trusting the results
3. Compare variable selection methods (Enter, Forward, Stepwise)
4. Verify that SPSS and Python produce consistent estimates

## Data

- **Source:** [Student Performance (Multiple Linear Regression)](https://www.kaggle.com/datasets/nikhil7280/student-performance-multiple-linear-regression) on Kaggle
- **Sample:** 8,000 of 10,000 records (80%)
- **Dependent variable:** Performance Index
- **Independent variables:** Previous Scores, Hours Studied, Sleep Hours, Sample Question Papers Practiced, Extracurricular Activities (Yes/No, dummy coded with No = 0)

Numeric predictors were standardized (Z-scores) so coefficients can be compared directly.

## Methodology

| Step | Method |
|---|---|
| Relationships | Pearson correlation matrix |
| Model fitting | OLS regression (statsmodels, SPSS) |
| Overall significance | ANOVA F-test |
| Coefficient significance | t-tests, standardized Beta |
| Multicollinearity | VIF, Tolerance |
| Heteroscedasticity | Breusch-Pagan, White test, residual plots |
| Residual normality | Shapiro-Wilk, histogram, Normal P-P plot |
| Autocorrelation | Durbin-Watson |
| Variable selection | Enter, Forward, Stepwise |

## Results

| Variable | Beta | Effect |
|---|---|---|
| Previous Scores | 0.921 | Strongest driver |
| Hours Studied | 0.385 | Second strongest |
| Sleep Hours | 0.042 | Small |
| Sample Papers Practiced | 0.028 | Small |
| Extracurricular Activities | 0.015 | Smallest |

All five predictors were significant at p < 0.001. All three selection methods kept all five variables and produced the same final model.

**Assumption checks:** VIF values were about 1.00 for every predictor (no multicollinearity), and Durbin-Watson was 1.989 (no autocorrelation). Residual plots were consistent with constant variance and normality.

**SPSS vs Python:** Coefficients, R², and the F-statistic matched. The intercept differed slightly (-0.015 in SPSS vs -0.018 in Python), with no effect on interpretation.

## Key Takeaways

- **Statistical vs practical significance.** With 8,000 observations, even tiny effects become significant. Sleep Hours has p < 0.001 but a Beta of only 0.042, so it matters statistically but barely in practice.
- **Model fit.** The model reaches R² = 0.989. This is far higher than typical real-world data, because the Kaggle dataset appears to be synthetic with the target built largely from the predictors. The value of this project is the testing workflow, not the fit.

## Tools

Python (pandas, NumPy, statsmodels, SciPy, scikit-learn, matplotlib, seaborn), SPSS, Excel

## Team

Annmaree Hadee, Weera Buapan, Rinrada Supong
