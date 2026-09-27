# Factors Influencing Student Academic Performance
### Multiple Linear Regression Analysis Using Python and SPSS

This project examines the factors influencing student academic performance through multiple linear regression, with comprehensive assumption testing and cross-validation of results between two statistical platforms.

Prepared as part of Data Analytics and Statistics 2 (SM340), Financial Engineering Program, University of the Thai Chamber of Commerce.

## Objectives

1. To develop a multiple regression model explaining the Performance Index from five independent variables
2. To test all classical regression assumptions prior to interpreting the results
3. To compare variable selection methods (Enter, Forward, and Stepwise)
4. To assess the consistency of estimates produced by SPSS and Python

## Data

- **Source:** [Student Performance (Multiple Linear Regression)](https://www.kaggle.com/datasets/nikhil7280/student-performance-multiple-linear-regression), Kaggle
- **Sample size:** 8,000 of 10,000 observations (80%)
- **Dependent variable:** Performance Index
- **Independent variables:** Previous Scores, Hours Studied, Sleep Hours, Sample Question Papers Practiced, and Extracurricular Activities (dummy variable, No = 0)

Continuous independent variables were standardized (Z-scores) to allow direct comparison of coefficients.

## Methodology

| Analysis | Method |
|---|---|
| Correlation analysis | Pearson correlation matrix |
| Model estimation | Ordinary Least Squares (statsmodels, SPSS) |
| Overall model significance | ANOVA F-test |
| Coefficient significance | t-test and standardized coefficients (Beta) |
| Multicollinearity | Variance Inflation Factor (VIF) and Tolerance |
| Heteroscedasticity | Breusch-Pagan test, White test, and residual plots |
| Normality of residuals | Shapiro-Wilk test, histogram, and Normal P-P plot |
| Autocorrelation | Durbin-Watson statistic |
| Variable selection | Enter, Forward, and Stepwise methods |

## Results

| Variable | Standardized Coefficient (Beta) | Relative Influence |
|---|---|---|
| Previous Scores | 0.921 | Highest |
| Hours Studied | 0.385 | High |
| Sleep Hours | 0.042 | Low |
| Sample Question Papers Practiced | 0.028 | Low |
| Extracurricular Activities | 0.015 | Lowest |

All five independent variables were statistically significant at p < 0.001. All three variable selection methods retained the same five variables and yielded an identical final model.

**Assumption testing:** VIF values of approximately 1.00 for all variables indicate no multicollinearity, and a Durbin-Watson statistic of 1.989 indicates no autocorrelation. Residual plots are consistent with the assumptions of homoscedasticity and normality.

**Comparison of SPSS and Python:** Both platforms produced consistent coefficients, R², and F-statistics. The intercept differed marginally (-0.015 in SPSS and -0.018 in Python), which does not affect the interpretation of the model.

## Discussion

- **Statistical versus practical significance:** Given the large sample size, variables with minimal effects still achieved statistical significance. For example, Sleep Hours was significant at p < 0.001 but had a standardized coefficient of only 0.042, indicating limited practical importance.
- **Model fit:** The model achieved an R² of 0.989, which is considerably higher than is typical for real-world data. This is likely attributable to the nature of the dataset, in which the dependent variable appears to be constructed largely from the independent variables. The primary contribution of this project is therefore the analytical and diagnostic process rather than the level of model fit.

## Tools

Python (pandas, NumPy, statsmodels, SciPy, scikit-learn, matplotlib, seaborn), SPSS, Microsoft Excel

## Project Team

Annmaree Hadee, Weera Buapan, Rinrada Supong
